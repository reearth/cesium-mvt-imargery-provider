# cesium-mvt-imagery-provider

## Usage

```ts
const imageryProvider = new MVTImageryProvider({
  urlTemplate: "http://localhost:8080/sample_mvt/{z}/{x}/{y}.mvt",
  layerName: "layerName",
  style: _feature => {
    return {
      strokeStyle: "green",
      fillStyle: "green",
      lineWidth: 1,
    };
  },
  onSelectFeature: _feature => {
    console.log("Feature is selected");
  },
  credit: "cesium.js",
});

const layers = viewer.scene.imageryLayers;
const currentLayer = layers.addImageryProvider(imageryProvider);
currentLayer.alpha = 0.5;

// Call `layers.remove(currentLayer);` when it is unnecessary.
```

See example directory for more details.

## Development

1. `yarn`
2. `yarn build`
3. `yarn link && yarn link "cesium-mvt-imagery-provider"`
4. `cd ./example`
5. `yarn && yarn dev`
6. Then example cesium application is started

If you run example, you need to set sample MVT data to `./example/public`.
And you should change `layerName` option for `MVTImageryProvider` in `./example/src/Imagery.tsx`.
