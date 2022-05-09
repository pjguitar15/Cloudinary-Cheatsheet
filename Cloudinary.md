### Cloudinary Configuration
- Click your profile picture on the upper right 
- Click on the gear icon (configurations)
- Go to upload tab
- Scroll down until you see the Upload presets section
- Click Add Upload Preset
- Set your upload preset name or just leave it as the default name
- Change the signing mode to unsigned
- Hit save

### Where to find Cloudinary Cloud Name
- Click your profile picture on the upper right 
- Click on the gear icon (configurations)
- Go to Account tab
- You can see it at the bottom of the page

### Upload image on react
```javascript
// handler function
const uploadImage = (files) => {
  // e.target.files returns an array
  console.log(files[0])
}

// jsx
<input type='file' onChange={(e) => { uploadImage(e.target.files) }} />
```

### Axios API Request
```javascript
// install it first using npm i axios
import Axios from 'axios'

// how to use axios. this is inside uploadImage function
const formData = new formData()
formData.append('file', files[0])
formData.append('upload_preset', 'presentNameHere')

const cloudName = 'pedro-machado-inc'
Axios.post(`https://api.cloudinary.com/v1_1/${cloudName}/image/upload`, formData)
.then((res) => console.log(res.data.url)) // res.data.url takes the image url
```

### Cloudinary React Package
> npm i cloudinary-react
```javascript
import { Image }  from 'cloudinary-react'
<Image cloudName='pedro-mechado-inc' publicId='https://res.cloudinary.com/somethingsomething' />
```

### Pass file object to a state
```javascript
<input onChange={(e) => setImageSelected(e.target.files)} />
```
