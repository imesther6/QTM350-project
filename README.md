# QTM350-project

## Introduction
Nowadays, we live in a digital world and often encounter fragmented information. Pictures seem to become the dominant media for delivering information.  However, comprehending words in pictures may not be an easy task since the words may not be in a good formating style or the image could be fuzzy. Therefore, we think it would be convenient to have computers help us read the words in the images and output an articulate text file. After we learned some machine learning services offered by AWS in QTM 350, we decide to use Textract as our solution. Thus, basically, by using Amazon service Textract, our project is trying to test whether background color, RGB differences between background color and text color, and pixel value would affect text detection confidence scores.

We start with an overview of the importance of the problem, the Amazon Web Services [Amazon Textract](https://docs.aws.amazon.com/textract/latest/dg/what-is.html), explain how it works, and then discuss the results we found.

## Textract Overview

Amazon Textract is a machine learning service that automatically extracts text, handwriting, and data from scanned documents that goes beyond simple optical character recognition to identify and extract data from forms and tables. Many companies today manually extract data from scanned documents such as PDFs, images, tables, and forms, or through simple OCR software that requires manual configuration which oftentimes requires reconfiguration when the form changes. To overcome these manual and expensive processes, Textract uses machine learning to read and process any type of document, accurately extracting text, handwriting, tables, and other data without any manual effort. One can quickly automate document processing and take action on the information extracted whether it be automating loans processing or extracting information from invoices and receipts. Textract can extract the data in minutes vs. hours or days. Additionally, one can add in human reviews with Amazon Augmented AI to provide oversight of your models and perform reviews for sensitive data. 

![picture](https://d1.awsstatic.com/Get-Cloud/Textract/product-page-diagram_Textract%402x.639922faebc8f38f768e38c3f620cc32725e8b0e.png)

In this report, we will also explore the data via visualization, ANOVA test, and regression analysis.

We have walked through what we have done about our project in our blog "TO BE FILLED". If you are interested in reproducing or furture modifying our work, please read this [blog](https://finalprojectqtm350.s3.amazonaws.com/qtm350_project.html).

## Data Collection and Preparation

We used the function of RGB Color Codes Chart on the [website](https://www.rapidtables.com/)  to find the colors we wanted for the text and background. Here, we will take the blue one as an example. Initially, we set the code for Red and Green to 0 and Blue to 150. Then, we fetched the color and set the color for the first Monday text. Afterward, we increased the code for Blue by 5 each time for 20 times until it reached 250 and used the colors for the other Monday texts. Now, we have 21 words with different blues whose code ranges from 150 to 250 with an increment of 5. To be exact, the colors had the Blue codes 150, 155, 160, 165, 170, 175, 180, 185, 190, 195, 200, 205, 210, 215, 220, 225, 230, 235, 240, 245, and 250. Next, we increased the code for Blue by 5 again to reach 255 and used that as the background color. Arranging the 21 words on the same page, we took a screenshot of the data and saved it as a PNG file. While I was using a MacBook, we could easily change the pixel of the image through image editing. The initial pixel was 144px so that we set the second picture's pixel to 130. Then, we decreased the pixel values by 10 each time for 10 times until it reached 30 and saved the 12 pictures. The final picture pixels were 144, 130, 120, 110, 100, 90, 80, 70, 60, 50, 40, and 30. Finally, we repeated the same process for Green and Red by setting the other two RGB colors to 0, changing code for the desired colors, and modifying the pixel for each picture.

## Code

If you want to only get the code we used, you can check [qtm350_project.ipynb](qtm350_project.ipynb), as all of our code are contained in that file.

## Architecture

The architecture of the AWS Textract Service we used in our project is presented in this [diagram](architecture.jpg).

## Images
If you want to get the source pictures that we analyzed, you can find them in the folder [image](image). For your downloading purpose, we have also zipped all source pictures into [image.zip](image.zip).
