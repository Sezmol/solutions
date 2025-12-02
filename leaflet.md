# Смена CRS без перемонтирования всей карты / Changing the CRS without remounting the entire map
const center = map.getCenter()
const zoom = map.getZoom()

map.options.crs = this.condition ? L.CRS.EPSG3395 : L.CRS.EPSG3857

map._resetView(center, zoom, true)

map.eachLayer(layer => layer.redraw?.())
