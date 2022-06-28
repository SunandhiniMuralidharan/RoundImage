# Round Image Library

## 1. Introduction
Round Image Library is a way to view image that supports rounded corners like circle or oval in OpenHarmony API Version 8. Rounded Image (Circle or Oval) has custom properties

The complete component implementation can be found [here](https://github.com/Applib-OpenHarmony/RoundImage)

## 2. Use Case
Such Rounded or Oval Images are used in profile picture of various social media login, thumbnails of various picture gallery, etc. Screenshot of the different ways to use the library is shown below


![Round Image](https://user-images.githubusercontent.com/71301091/176164422-57524530-f60e-4772-be25-988813c40057.jpg)


## 3. Installation
To use this library, please install using the below instruction.
```js
npm install @ohos/libroundimage --save
```
For details about Open Harmony NPM environment configuration, see [here](https://gitee.com/openharmony-tpc/docs/blob/master/OpenHarmony_npm_usage.md)

## 4. Import
```js
import { RoundImage, OvalImage, RoundImageModel, OvalImageModel, ClickListener } from '@ohos/libroundimage'
```

## 5. Directory Structure

````
|---- RoundImageView
|     |---- libroundimage 
|           |---- src
|                 |---- clickListener.ets
|                 |---- OvalImageModel.ets
|                 |---- roundImage.ets
|                 |---- RoundImageModel.ets
|     |---- entry
|           |---- src
|                 |---- main
|                       |---- MainAbility
|                             |---- pages
|                                   |---- index.ets
````

## 6. Library Usage

### Round Image

#### Import
```js
import { RoundImage, RoundImageModel, ClickListener } from '@ohos/libroundimage'
```

#### Code
```js
//Initialize the model
model: RoundImageModel.Model = new RoundImageModel.Model();

//Set the properties of the image using setter methods of the model
this.model.reset()
this.model.setSrcPath(this.imageResource)
this.model.setBorderRadius(this.borderRadius)
this.model.setNeedBorder(true)
this.model.setBorderWidth(10)
this.model.setBorderColor('#0000FF')
this.model.setImageWidth(this.imageWidth)
this.model.setImageHeight(this.imageHeight)
this.model.setObjectFit(this.objectFit)
this.model.setClickListener({
    onClick() {
        console.info('onClick event reached app')
        prompt.showToast({
          message: 'Round Image is clicked'
        })
    }
})

//Use the Round Image component by passing the model created above
RoundImage({
  model: this.model
})
```

### Oval Image
Image is constructed using Image Bitmap. The display shape is constructed using the Bezier Curve to make into Oval shape and then the Image is fitted into the shape.

#### Import
```js
import { OvalImage, OvalImageModel, ClickListener } from '@ohos/libroundimage'
```

#### Code
```js
//Initialize the model
model_oval: OvalImageModel.Model = new OvalImageModel.Model();

//Set the properties of the image using setter methods of the model
this.model_oval_second.reset()
this.model_oval_second.setSrcPath(this.imageSource)
this.model_oval_second.setImageWidth(this.ovalImageWidth1)
this.model_oval_second.setImageHeight(this.ovalImageHeight1)
this.model_oval_second.setNeedBorder(true)
this.model_oval_second.setBorderWidth(5)
this.model_oval_second.setBorderColor('#0000FF')
this.model_oval_second.setClickListener({
  onClick() {
    console.info('onClick event reached app')
    prompt.showToast({
      message: 'Oval Image is clicked'
    })
  }
})

//Use the Oval Image component by passing the model created above
OvalImage({
  model: this.model_oval_second
})
```

## 7. Compatibility
Supports OpenHarmony API Version 8
