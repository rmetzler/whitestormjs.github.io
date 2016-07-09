<h2 class="ws" id="model">Model [Class]</h2>

> WHS.Model example:

```javascript

var teapot = GAME.Model({

    geometry: {
        path: "assets/models/utah-teapot-large.json",
        physics: "assets/models/utah-teapot-light.json"
    },

    mass: 10,

    material: {
        vertexColors: THREE.VertexColors,
        shading: THREE.SmoothShading,
        map: WHS.API.texture('assets/textures/teapot.jpg', {repeat:{x: 2, y:2}}),
        kind: "phong",
        side: THREE.DoubleSide,
        useCustomMaterial: true,
        rest: 0,
        fri: 1
    },

    pos: {
        x: 0,
        y: 100,
        z: 0
    },

    scale: {
        x: 4,
        y: 4, 
        z: 4
    }

});

```


`WHS.Model` class loader for loading objects in JSON format.

Model is a simple class too. But it doesn't depends on `Three.js geometry` object. It loads geometry from `JSON` file by url as it's material, but material you can replace with your own. Just add `useCustomMaterial` property with `true` value in `material` parameter object.

Parameter      |       Default        | Type               | Description |
-------------- | -------------------- | ------------------ | ----------- |
**path**       | ""                   | `String`(url)      | Url adress to model JSON file.
**physics**    | ""                   | `String`(url)      | Url adress to physics model JSON file.

**physics** parameter is used for adding shape that will be calculated in Physi.js. Usually it is used to defining light variant of existing model, so physics will work faster. If you don't type **physics** parameter - it will be replaced with **path**.

<aside class="notice"><code>scale</code> parameter will be also applied to physics shape, but it can be changed only in three.js mesh.</aside>

Also, if model has vertex colors - you can add `useVertexColors` property to material parameter object (as with `useCustomMaterial`).

Similar one is `WHS.Morph`. It's like a model, but this one supports animations.

<img src="images/shapes/model.png" alt="physics and for rendering model created with whitestorm.js">