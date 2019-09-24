# npfPhotosets()
npfPhotosets() is a plugin for styling Tumblr photosets like the layout observed on the website's dashboard. It focuses on photosets created through NPF(Neue Post Format), Tumblr's new format, which allows you to create photoset's through the entire post body instead of only at the top of it when you're the original poster; however, it can also be applied to Legacy photosets.
## Use case
Include both the JavaScript and the CSS file in your code, then call the function and it's parameters:
```
var npfOptions = {
   rowClass:"npf_row",
   imageContainerClass:"tmblr-full",
   generatedPhotosetContainerClass:"npf_photoset",
   imageClass:"npf_image",
   includeCommonPhotosets: true,
	useTumblrLightbox: true,
   insertGalleryIndicator: false,
   galleryIndicatorClass: "npf_gallery_indicator",
   galleryIndicatorContent: "<img src='image_url'>",
   photosetMargins:""
}

npfPhotosets("postSelector", npfOptions);
```
## Options
- `"postSelector"` is where the selector used for your posts goes, between quotes as suggested. It can be a mere HTML selector(like `“article”`), a class(`“.posts”`), or even an array-like list.
- `rowClass` is where the name of the class of Tumblr’s generated row wrappers should be inserted. There is no need to change this unless Tumblr changes its used class name.
- `imageContainerClass` is where the name of the class of Tumblr’s generated full-size image wrappers should be inserted. There is no need to change this unless Tumblr changes its used class name.
- `generatedPhotosetContainerClass` is where the name of the class to be assigned to the generated photoset wrappers should be inserted. It is presented by default as npf_photoset but if anyone feels the need to use a different class name, it should be changed here. Note that this allows only one class.
- `imageClass` is where the name of the class to be assigned to each photoset image should be inserted. It is presented by default as npf_image but if anyone feels the need to use a different class name, it should be changed here. Note that this allows only one class.
- `includeCommonPhotosets` should have either a true or false value. If true, this will allow photosets made with the Legacy post format to be styled through this plugin. For this to work correctly, you must make sure your photosets share the same class names used for NPF photosets' elements, as well as adding to the photoset container the `data-layout` attribute with the `{PhotosetLayout}` value.
- `useTumblrLightbox` should have either a true or false value. If true, this will allow all photosets to use the built-in Tumblr function for inserting lightboxes.
- `insertGalleryIndicator` should have either a true or false value. If true, this will insert a div into each image container where you can put an indication that there is an image gallery with a lightbox link. If you’d rather have no indicator, change this to false.
- `galleryIndicatorClass` is where the name of the class to be assigned to each gallery indicator div should be inserted. It is presented by default as npf_gallery_indicator but if anyone feels the need to use a different class name, it should be changed here. Note that this allows only one class.
- `galleryIndicatorContent` is where you can insert content inside the gallery indicator div, such as text or an icon. The inserted `<img>` tag is merely an example.
- `photosetMargins` is where the value of the margins between photos inside the photosets should be inserted. The value is measured in pixels. If you want it to have no margins, insert a 0; in case you leave it empty(like two quotation marks with nothing in-between `“”`), it will automatically use an adaptable percentage based value for the margins. You should always keep the quotation marks, even in the no margins case.

The options `rowClass` and `imageContainerClass` are available for easy maintenance reasons.

As of 24/09/2019, `includeSingleRowImagesInPhotosets` has been removed.
