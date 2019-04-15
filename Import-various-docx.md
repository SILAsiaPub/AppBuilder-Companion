# Importing .docx files not purpose built for RAB

### Questions to think about before starting

- Do you have the rights to publish the contents?
- Why do you want your content in an app?
  - If it is just text and pictures. Would an ePub2 or ePub3 format suffice? Why not?
  - Could you content just be handled as HTML?
  - If you have audio too then it may be worth putting it in an app. But ePub also can support audio.
  - RAB does generally add improved navigation over an ePub.
  - Do you want audio playback syncronized with text highlighting? RAB can do that but also make an ePub that can do that too.

### RAB .docx handling

The Word .docx import in RAB is set up for picture books (one picture per page)  where each page has a picture locked at the top and text below.

If you have a document that has pictures at various places in the text, it is unlikely to suit a picture book style. 

### Going ahead with an app

- You need to add pages/chapters to the document by putting in hard page breaks. 

- Do you what a picture book format? 
  - If **yes** then you must have only one picture per page. If the picture is portrait format you may need to change it into a landscape format so you have room for text on the page.
  - If **no**, then you need to remove the picture/s in Word and replace with a paragraph with the following in the paragraph `\fig picturename.jpg\fig*`. Those picture files will need to be added into the **Illustrations** tab of the **Images** section.