# aframe-ground-component

This component provides various sweet looking options for ground in an [A-Frame](http://aframe.io) VR scene (no sky, lights or dressings).

This is a fork of the [aframe-environment-component by Feiss](https://github.com/feiss/aframe-environment-component/). The `environment` component is awesome, but sometimes dressings, sky and lighting is just not needed for your scene so I decided remove those other features and focus on a simpler version.

There are 2 new parameters to add more control over ground placement height (`positionY`)and scale (`groundXZScale`). 

Make sure you are using __A-Frame 0.9.2__ or later. Then just include `aframe-ground-component.js` in your HTML:

```html
  <script src="https://unpkg.com/aframe-ground-component@0.0.4/dist/aframe-ground-component.min.js"></script>
```

and add the `ground` component to an entity:

```html
  <a-entity ground></a-entity>
```

That's it! :)


## Presets

The previous code will setup a default scene, but you have a bunch of already predefined presets to choose from, using the `preset` parameter, like this:


```html
  <a-entity ground="preset: <name of the preset>"></a-entity>
```

You can view and try all the presets in the **[aframe-ground-component Test Page](https://kfarr.github.io/aframe-ground-component/)**. The current list of presets are listed in the next section.


## Parameters

Apart from using a preset, you can tweak the ground with many parameters, like this:

```html
  <a-entity ground="groundColor: #445"></a-entity>
```

You can also select a preset but change some of its parameters:
```html
  <a-entity ground="preset: forest; groundColor: #445; grid: cross"></a-entity>
```

This is the list of the available parameters.


| Parameter   | Default | Description |
|-------------|---------|-------------|
| **active**  | true    | Show/hides the component. Use this instead of using the `visible` attribute |
| **preset**      | 'default'  | Valid values: `none`, `default`, `contact`, `egypt`, `checkerboard`, `forest`, `goaland`, `yavapai`, `goldmine`, `threetowers`, `poison`, `arches`, `tron`, `japan`, `dream`, `volcano`, `starry`, `osiris` |
| **seed**        | 1       | Seed for randomization. If you don't like the layout of the elements, try another value for the seed.  |
| **shadow**  | false | Shadows on/off. Sky light casts shadows on the ground of all those objects with `shadow` component applied |
| **shadowSize** | 10 | Shadows size |
| **flatShading** | false | Whether to show everything smoothed (false) or polygonal (true). |
| **playArea** |  1    | Radius of the area in the center reserved for the player and the gameplay. The ground is flat in there and no objects are placed inside.|
| **ground**  | 'hills' | Valid values: `none`, `flat`, `hills`, `canyon`, `spikes`, `noise`. Orography style. |
| **groundYScale** | 3  | Maximum height (in meters) of ground's features (hills, mountains, peaks..) |
| **groundXZScale** | 1  | Integer amount by which to scale the ground in X and Z axes |
| **groundTexture**| 'none' | Valid values: `none`, `checkerboard`, `squares`, `walkernoise`|
| **groundColor** | '#553e35'  | Main color of the ground |
| **groundColor2**| '#694439'  | Secondary color of the ground. Used for textures, ignored if `groundTexture` is `none` |
| **grid**    | 'none'  | Valid values: `none`, `1x1`, `2x2`, `crosses`, `dots`, `xlines`, `ylines`. 1x1 and 2x2 are rectangular grids of 1 and 2 meters side, respectively.  |
| **gridColor** | '#ccc' | Color of the grid. |
| **positionY** | 0  | Specify custom height for ground |


The best way to work with them is to press `ctrl-alt-i` to open the [inspector](https://aframe.io/docs/master/introduction/visual-inspector-and-dev-tools.html#a-frame-inspector), search for 'ground' in the filter box and select it, and tweak the parameters while checking the changes in realtime. When you are happy, you can use the `Copy attributes` button or even better, copy the attributes logged in the browser's dev tools console.

## Performance
This component removes all dressings used in environment component so it should perform OK.

## Original Credit

This was originally written as environment component by @fiess at [aframevr in Slack](https://aframe.io/slack-invite) or [Discord](https://supermedium.com/discord).
