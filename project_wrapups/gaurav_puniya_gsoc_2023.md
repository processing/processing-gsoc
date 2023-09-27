
# Adding AR Markers and Migrating VR Library[WIP]

| **Project** | [Adding AR Image Markers and Migrating VR Library](https://summerofcode.withgoogle.com/programs/2023/projects/5DBKH7wz) | 
| :--- | :--- |
| **Student** | Gaurav Puniya|
| **Github** | [p4puniya](https://github.com/p4puniya)  |
| **Organisation**  | [Processing Foundation](https://processingfoundation.org/)  |
| **Mentors** | [Aditya Rana](https://github.com/ranaaditya), [Andrés Colubri](https://github.com/codeanticode) |
| **Repo**| https://github.com/p4puniya/processing-android |
| **Discussions**| [AR-Image Markers](https://github.com/processing/processing-android/discussions/743) |
| **Merged PR** | https://github.com/processing/processing-android/pull/745 |


## Overview
The project entailed migrating the VR library from Google VR(deprecated in 2019) to Cardboard SDK, and adding Image Marker functionality to AR library. This was to be done in broadly two parts:  
1. Adding AR-Markers:
* Create a function to load the dataset for augmented images.
* Add trackables to the images.
* Update trackables with 3D-models.
2. Migrating VR-Library:
* Import the Cardboard SDK.
* Create a JNI bridge between existing Processing-android and Cardboard SDk codebase.
* Update the existing VR templates in android-mode and add new templates for JNI Bridge.
* Add C++ support to the VR library.
* Map the new methods( from Cardboard-SDK) to their predecessors( from GVR).
* Migrate the methods to the new SDK.
* Test the cardboard integrations on real android devices vigorously.
* Add new sample apps for VR in andorid-mode
* Update andorid references for VR if required


## Tasks Completed
* **Successfully incorporated image markers functionality in AR library.**
![AR markers test image](https://github.com/p4puniya/processing-gsoc/blob/main/project_wrapups/267441841-f02343ec-9300-4206-8ddb-174f83788dc3.png)

## TODO 
* Add Image Markers to AR Library:
- [x] Create a new function to load the dataset containing the reference images for Augmented Images.
- [x] Update ARTrackable.java and ARTracker.java to support trackable type: Image.
* Migrate VR Library from GVR to Cardboard SDK:
- [ ] Import cardboard SDK to processing android.
- [ ] Update the existing VR templates and add new templates to make it compatible with C++/Android NDK.
- [ ] Create JNI Bridge between processing-android core/VR and Cardbaord SDK codebase.
- [ ] ...Continue Edits...

## Challenges
* As the coding period progressed, we discovered that the Cardboard SDK is implemented for the Android NDK for performance and not supporting everything initially like GVR was doing, i.e. all the methods for Cardboard were written in C/C++. It also don't have any proper documentation and Migration docs as of now. As this increased the project complexity, we decided to extend our GSOC timeline.
* Whilst adding the Image Markers, I came to know that Image types were never used for AR Trackables in P-Android. It worked only for planes, thus most of the methods that used AR planes were to be changed to use a new object(Trackable) and new methods were created to check whether the trackable object was an image or a plane.

## PRs 
* https://github.com/processing/processing-android/pull/749 (For Code review: Closed)
* https://github.com/processing/processing-android/pull/745 (Pull Request: Merged)

## Contribution & Next Steps
With AR Image Markers successfully merged into the main branch, I move on to migrating the VR libraries. Some future prospectives for the AR Markers could be:
- [ ] Test for any abnormalities in Image Markers.
- [ ] Add documentation/tutorial for Image Markers to the processing android [website](https://android.processing.org/tutorials/ar_intro/index.html).

## Conclusion and Acknowledgements
From not being able to setup processing in my [local system](https://github.com/processing/processing-android/issues/732) to getting selected as a [GSoc contributor](https://medium.com/@ProcessingOrg/announcing-google-summer-of-code-2023-projects-75080c1554aa) and getting my first PR for it [merged](https://github.com/processing/processing-android/pull/745)...It's been a long, exciting and exceptional journey!  
I gained experience in using AR-Core, using AVD, learning more about markerless AR models and creating JNI bridge, android NDK, integrating C++ classes in Java projects, gaining indepth knowledge of Cardboard SDK and a lot more... 
Though I did feel overwelhmed at times, my mentors actively cleared my doubts and guided me well. I would like to offer my sincere gratitude to **Aditya Rana** and **Andrés Colubri** for their invaluable help and guidance throughout this google summer of code program. Aditya acted as an active support and constantly guided me in the right direction while Andrés reviewed my codes and helped me with the final touch-ups. I am extremely grateful to the Processing Community for letting me be a part of this **Amazing Family**. 

## Useful Links
* [Weekly reportes](https://medium.com/@gauravpny/processing-android-weekly-reports-86f2abcfdd38)
* [An Indepth study of the AR-Core's Augmented Image class](https://medium.com/@gauravpny/in-depth-study-of-ar-augmented-image-class-file-from-arcore-caeb1b88f10)
* [What are Augmented Images and How to add them to Processing](https://medium.com/@gauravpny/what-are-augmented-images-and-how-to-add-them-to-processing-android-8158a2e0dd90)
* [Progress Update during the Month of August](https://medium.com/@gauravpny/ar-markers-progress-update-352ccfe6e707)
