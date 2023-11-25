<script>
  // @ts-nocheck

  import { LeafletMap, TileLayer, Marker, Icon } from "svelte-leafletjs";

  const mapOptions = {
    center: [34.67977073888905, -92.744662386803],
    zoom: 5,
  };
  const tileUrl = "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png";
  const tileLayerOptions = {
    minZoom: 0,
    maxZoom: 20,
    maxNativeZoom: 19,
    attribution: "© OpenStreetMap contributors",
  };

  const iconOptions = {
    iconUrl: "/assets/icons/icon-map-pin.svg",
    iconSize: [40, 48],
    iconAnchor: [20, 41],
    popupAnchor: [1, -34],
    tooltipAnchor: [16 - 28],
  };

  let leafletMap;
</script>

<div class="contact-map" id="map">
  <LeafletMap bind:this={leafletMap} options={mapOptions}>
    <TileLayer url={tileUrl} options={tileLayerOptions} />
    <Marker latLng={[36.03899518086081, -86.54156145928226]}
      ><Icon options={iconOptions} /></Marker
    >
    <Marker latLng={[31.530044775340983, -99.19332872451014]}>
      <Icon options={iconOptions} />
    </Marker>
  </LeafletMap>
</div>

<style>
  .contact-map {
    width: 100vw;
    /* height: 97.87vw; */
    height: 367px;
    max-width: 1920px;
  }

  @media screen and (min-width: 768px) {
    .contact-map {
      width: calc(100vw - 192px);
      height: 560px;
    }
  }

  @media screen and (min-width: 1280px) {
    .contact-map {
      width: calc(100vw - 330px);
    }
  }
</style>
