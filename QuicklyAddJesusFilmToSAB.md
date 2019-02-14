## HOW TO place links to JESUS Film clips into Luke's Gospel of your Scripture App

1. Open [this Google Sheet](https://docs.google.com/spreadsheets/d/14aO6sksehH0M3McxJyAJFLkQdjrPRC6D-gjahNjO7Bk/edit#gid=0) and create your own copy (File &gt; Make a copy…) and renaming it appropriately (replace XYZ with appropriate ISO code)
2. Use the Drop-Down menu in cell C5 to select a project
3. First delete the Clip Titles in column C, and [optionally] fill in your vernacular Clip Titles. If these are blank, then just the reference range will be displayed below each clip in the app.
4. Check, and if needed, adjust the references in Columns E and F. Don’t change/translate the book code LUK - as this needs to remain as is - but feel free to change the chapter/verse numbers as needed. If you need to see what exactly the clip contains, then you can click on the link in Column G.
5. Once you are satisfied that everything is in order, you can Select and Copy (Ctrl-C) the generated XML code in Column H (cells H7..H67)

...there’s more on the next page...

![Image](https://lh4.googleusercontent.com/ZLhQWI3ptjeSCQil1kYkAnv0JrmhrA1NSTRUhZrY74a-0hyWMhFBSYvcKPX7aL47Pio80X2RaZ4tSJkw1OTtI0VMjP4-JH2tvvxCx_mfm2PtHMXsjHsLPUP3-_DrR3k6b9O90j9z)

6. If you don’t already have videos included in your Scripture App, then add a link to a “dummy” video to the App definition as shown below:

![Image](https://lh6.googleusercontent.com/DLiHWuHLJgyPCZKrxa7CB6kPN7ZpaZvcCnjD0cx8qrnCnFifrp6TpEMKTgX1HnYWuxHyBVzPcAWahnWHFzUntAWONhzZpSKVALVIqzvH4yXoE560LU6h7brTEite6NFGk5rRxP11)


7. After making sure the SAB project has been saved, and SAB has been closed, locate your App Definition file {ProjectName.appDef} for the project.
This is usally stored at a location like this: C:\My Documents\App Builder\Scripture Apps\App Projects\{ProjectName}
8. Open this file with a text editor (Notepad++ is recommended).
9. Search for &lt;videos&gt; in order to locate the place where the XML code needs to be pasted, and select the lines containing the “dummy” video:
```XML
  <videos>
    <video id="TestVideo">
      <title>TestTitle</title>
      <online-url>http://test.url</online-url>
      <placement pos="before" ref="HalbiDev|MAT.1.1"/>
    <video>
  </videos>
 ```
10. Ensuring you leave the &lt;videos&gt; and &lt;/videos&gt; tags in place, Paste the XML (copied from the Google Sheet) into this section.<br/>
It should look something like this:

![Image](https://lh6.googleusercontent.com/ARn1Cueywbu9GEfZho-VgM7qjlfL-Puq8H05glI1uWYPMpyFYAqmCCqA6cRCx5aSmoh8jNaqQKUMh9VPYO1UovDrp5wj1nmGC0wLlft54OP8aYyxgAPaNeUPbLNsQv4rr5SU1qoQ)
11. Now SAVE this .appDef file and close it.
12. Almost everything is in place, except that you need to copy/install the JESUS Film Thumbnail images into the appropriate folder within your SAB project definition. These can be downloaded from here ([4MB zipped folder](https://drive.google.com/open?id=1W_b-qL33zazB1d85imQ7AWoBrQQYkp-c)) or if you prefer to keep the App slightly smaller, the same thumbnails are available at a smaller (400px wide) size from here ([1.3MB zipped folder](https://drive.google.com/open?id=1C0_H1mqYKFi3fIP_Ud-shWgrV8hiKx_a)). Ensure that these 61 Thumbnails are located within the video folder of the SAB Project_data folders as shown below:

![Image](https://lh5.googleusercontent.com/BJVPTv_4eKQRSzKQa2_SZTu_e-GsKuw9Vs6L4Rk_vgCL2UGJxVrMNZrumwzTuKe2X4PDPOz8z1YSAr0s7fiEhHJskJQCB1pqVeaOTLEsvu5k9iXRYPaUb6m8UFOj6z0WQWIBnITB)

13. Now, re-open the Scripture App Builder and check that the clips are included in the project definition as expected:

![Image](https://lh4.googleusercontent.com/SIXOLQRHFIge-nSgxVSd5Qp94IlKB5EhHQNncz1-Y85OadtL2RY_SCP-QuEtEDpnKfx883mAa3g7m3cTyA87WwdrzhpUHDsid6y-mUk009SG8I1IXzO8f6lwe1RcFAA8iHt6bjNR)

14. If your App doesn’t normally connect to the Internet for downloading (audio) files, you may be caught out by a (known) bug in SAB that does not trigger adding the appropriate permissions to the App (even when we add video links). So a workaround is to add an audio download source, and then add an audio file, which will trigger the appropriate permissions to be set for the App.
[Note that if you don’t do this, then the App will build successfully, but when the user clicks on the Video links, nothing will happen.]

![Image](https://lh3.googleusercontent.com/tvBHZf5uget_OlLbrPp8K9tOBAnMUZfj3nBZX_hef7itb59wr8U3PcxChc4drcGAHUPHtqAPZLTBt7euy2gNytodQZd27un2bdW1dUaBIevg-mUR64E6JX95RMCFegFIkQdjFZWD)

Feedback via comments in this document would be appreciated.
- Contributed by Mark Penny
