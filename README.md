
Android Image Slider
Just add the images you want to view.

Easy to use.
Automatic scrolling for the time you set.
Add any caption to the images.
14 different slide animations.
Adjust corner radius images.
Use with Java or Kotlin.

Android Arsenal license  Codacy Badge

Usage
Add ImageSlider to your layout
<com.denzcoskun.imageslider.ImageSlider    
     android:id="@+id/image_slider"    
     android:layout_width="wrap_content"    
     android:layout_height="300dp"    
     app:iss_auto_cycle="true"    
     app:iss_period="1000"    
     app:iss_delay="1000"    
     app:iss_text_align="CENTER"/>  
You can change placeholder image.
 app:iss_placeholder="@drawable/placeholder"  
You can change error image.
 app:iss_error_image="@drawable/error"  
You can change indicators.
app:iss_selected_dot="@drawable/default_selected_dot"  
app:iss_unselected_dot="@drawable/default_unselected_dot"  
Add ImageSlider to your Activity
val imageList = ArrayList<SlideModel>() // Create image list  
  
// imageList.add(SlideModel("String Url" or R.drawable)  
// imageList.add(SlideModel("String Url" or R.drawable, "title") You can add title  
  
imageList.add(SlideModel("https://bit.ly/2YoJ77H", "The animal population decreased by 58 percent in 42 years."))  
imageList.add(SlideModel("https://bit.ly/2BteuF2", "Elephants and tigers may become extinct."))  
imageList.add(SlideModel("https://bit.ly/3fLJf72", "And people do that."))  
  
val imageSlider = findViewById<ImageSlider>(R.id.image_slider)  
imageSlider.setImageList(imageList)  
You can change scaleType for all images or one image.

import com.denzcoskun.imageslider.constants.ScaleTypes // important  
  
// FIT, CENTER_CROP or CENTER_INSIDE  
  
imageList.add(SlideModel("String Url" or R.drawable, ScaleTypes.FIT) // for one image  
imageList.add(SlideModel("String Url" or R.drawable, "Title", ScaleTypes.FIT) // you can with title  
  
imageSlider.setImageList(imageList, ScaleTypes.FIT) // for all images  
You can change title background on xml.

 app:iss_title_background="@drawable/gradient" //or app:iss_title_background="@android:color/holo_red_light"  
Also change text color on xml. It is default white.
 app:iss_text_color="#FFA0A0"   
Indicators can be remove.
 app:iss_no_dots="true"   
You can use click listener or double click listener.
imageSlider.setItemClickListener(object : ItemClickListener {    
    override fun onItemSelected(position: Int) {    
        // You can listen here.  
 }      
    override fun doubleClick(position: Int) {    
       // Do not use onItemSelected if you are using a double click listener at the same time.    
       // Its just added for specific cases.   
       // Listen for clicks under 250 milliseconds.  
 } })  
You can add animation like that, 14 Animations added. You can check in Animation List
imageSlider.setSlideAnimation(AnimationTypes.ZOOM_OUT)  
You can add stop and start auto sliding again.
imageSlider.startSliding(3000) // with new period  
imageSlider.startSliding()  
imageSlider.stopSliding()  
Setup
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}

dependencies {
	implementation 'com.github.denzcoskun:ImageSlideshow:0.1.2'
}
📄 License
Copyright 2019 Deniz Coşkun

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

License

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
