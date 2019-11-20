---
layout: post
title:  "Building an easily sharable interface to gather labels from humans."
date:   2019-05-14 11:31:47 -0500
categories: tutorial
featured-image: /building-an-easily-sharable-interface-to-gather-labels-from-humans/project.png
mathjax: true
---

![Figure 1.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/project.png){: .center-image}
*Figure 1. The home page of the interface we will build in this tutorial.  Check it out here: [https://www.zooniverse.org/projects/city-of-peacetopia-ornithophobia-project](https://www.zooniverse.org/projects/dwright04/city-of-peacetopia-ornithophobia-project)*


## Introduction ##

At some point in any machine learning project humans will need to look at the data.  Maybe you need to gather class labels or bounding boxes for supervised learning to begin with.  Or perhaps you need to check your dev set for examples with incorrect labels.  It could be that you want to measure the human-level performance on your test set as an estimate for the optimal (or Bayes) error rate.

This post will demonstrate how you can easily build a web-based interface, that is easily customisable using the [Zooniverse Project Builder](https://www.zooniverse.org/lab).  The figure above shows the home page for the project I built as an example for this post.  The project you build will have a shareable url that will allow your friends, family, classmates or co-workers ( or all of the above) to access your project in case you need to crowdsource some help.  Here's the link to my example project:

[https://www.zooniverse.org/projects/dwright04/city-of-peacetopia-ornithophobia-project](https://www.zooniverse.org/projects/dwright04/city-of-peacetopia-ornithophobia-project)

This project is designed to be a template. The idea for this particular example project was motivated by the third [deeplearing.ai course on coursera, Structuring Machine Learning Projects](https://www.coursera.org/learn/machine-learning-projects?specialization=deep-learning). In particular, the idea came from the Week 1 assignment, Bird recognition in the City of Peacetopia (case study).

Building this project is as easy as signing up for a Zooniverse account, filling out a series of web forms, adding some images to make the interface look pretty and uploading your data. Thats it! and it's free.  You can pay it forward by helping scientists and getting involved with [one of the citizen science projects hosted by Zooniverse.](https://www.zooniverse.org/projects)

## Project Building ##

First thing is to sign-up for a Zooniverse account if you haven't already.  This allows you to build and own projects.  There is no need to have an account to in order to classify, but if you want to be able to link individual classifications back to who made them (perhaps you want to know which classifications were made by experts) then you will want to encourage participants in your project to also sign-up for an account. 

Now that you have an account and logged-in, click the "Build a project" button highlighted in the image below.

![Figure 2.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/pb_button.png){: .center-image}
*Figure 2. Zooniverse projects page.*


This will take you to the project builder page.  The image below shows how my project builder page looks like.  It lists all the projects that I have built.  To build a new project click the "Create a new project" button.

![Figure 3.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/pb_0.png){: .center-image}
*Figure 3. Zooniverse project builder.*


This loads a page that looks something like the image below.  This page contains a series of fields to fill out.  This is all very straight forward and builds the home page of your project.  You can see what I have entered into these fields in the image.  By navigating to the [project](https://www.zooniverse.org/projects/dwright04/city-of-peacetopia-ornithophobia-project) you can see how this appears. 

![Figure 4.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/pb_1.png){: .center-image}
*Figure 4. Project builder main page.*


The panel on the left takes you to similar pages that set up various features and other pages for your project.  I'll show the three additional pages that are required to get a basic project going.  First we need to add a workflow to the project.  The workflow page will be used to set up the actual classification task and interface.  The workflow page is accessed by clicking on the workflow link highlighted by arrow <span style="color:red">**1**</span> in the image above.  On the next page click "New workflow" and give the workflow a name.  This loads the page below, which is used to build the classification interface.

## Workflows ##

![Figure 5.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/pb_2.png){: .center-image}
*Figure 5. Workflow interface.*


To set-up the classification interface we need to first select the task.  Click the "+Add a task" button.  There are four task types to choose from 1) Question, 2) Drawing, 3) Text and 4) Survey.  The two most common are question and drawing tasks and I'll focus on a question task in this post.  For the record text tasks are for document transcriptions (see the [African American Civil War Soldiers project](https://www.zooniverse.org/projects/usct/african-american-civil-war-soldiers) for example) while survey tasks are for classification tasks with many classes (for example see [Snapshot Debshan](https://www.zooniverse.org/projects/meredithspalmer/snapshot-debshan)).  In the image below I have set up a question task that is designed to gather the data that would be needed for the City of Peacetopia to train a classifier to determine when birds are flying overhead. There is help text for each of the fields on the page.  At a minimum you need to fill out the "Main Text" and "Choices" fields.  Under "Choices" there are options "Allow hiding marks", "Allow multiple" and "Required".   We can ignore "Allow hiding marks" which is only relevant for drawing tasks. For this example we can also ignore "Allow multiple", but if your particular classification task might contain images with multiple classes in them then this would allow users to select multiple answers for each image.  Checking "Required" means that users must select an answer before they can proceed to the next image.  The final requirement for a funtioning workflow is to link your data set to it.  You do this in the "Associated Subject Sets" field.  A subject set contains all the images (or subjects) for classification.  Once a subject set has been created it will be listed here and you simply check the box beside the name of the subject set you wish to link to this workflow. We'll look at building a subject set in the next section.

Before that, one final thing to consider is the retirement limit for the workflow.  The retirement limit determines how many users need to classify each image before it is considered fully classified and retired from the project, this is to avoid the case where people are needlessly labelling images that have been seen by many others.  The correct will depend on the difficulty of the task and who will be labelling the data.  For example a low retirement limit makes sense if everyone labelling the data is an expert at the task.  In practice a value of 10 works well, although this means you need at least 10 different people labelling your data.  You can always add your data back into the project if you need more labels per image to improve accuracy or reduce the retirement limit if it is taking too long.  The retirement limit is set at the bottom of the workflow interface in the "Subject retirement" field.

## Subject Sets ##

![Figure 6.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/pb_3.png){: .center-image}
*Figure 6. Subject set interface.*


To build a subject set click on "Subject Sets" on the left panel, arrow <span style="color:red">**2**</span> in Figure 4.  This takes you to the page shown above.  You can simply drag and drop your images into the light grey area.  There is one small complication in that you must include a manifest.  The manifest is a [csv](https://en.wikipedia.org/wiki/Comma-separated_values) file containing a column with the file name of each image in the data set and an arbitrary number of additional columns containing metadata.  Below is an example for the subject set linked to the example project.

```
subject,metadata
subject_0.png,metadata
subject_1.png,metadata
subject_10.png,metadata
subject_11.png,metadata
subject_12.png,metadata
subject_13.png,metadata
subject_14.png,metadata
subject_15.png,metadata
subject_16.png,metadata
subject_17.png,metadata
subject_18.png,metadata
subject_19.png,metadata
```

The file contains a header for the two columns.  I've added a metadata column for demonstration purposes with placeholders.  This metadata file must be dragged and dropped into the project builder at the same time as the images. Once thats done click "Upload new subjects".  You should now be able to see the newly created subject set from the workflow interface and now able to link the data.  After all that, it should now possible to test the workflow and see what it will actually look like.  To do this click on the "Test this workflow" button at the very bottom of the page.

## Making your project sharable ##
Once you are happy with how the project looks, its time to make it sharable.  Navigate to the visibility interface by clicking the "Visibility" link in the panel on the left highlighted with arrow <span style="color:red">**3**</span> in Figure 4.  The interface should look like the image below.

![Figure 7.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/pb_4.png){: .center-image}
*Figure 7. Visibility interface.*

Select "Public" if you want an easily sharable link.  But be careful, anyone on the web can plausibly access your project.  If your project contains proprietary data for example it may be best to keep the project as private, in which case you can allow others to access it by adding them as collaborators.  You can do this by going to the collaborators interface accessed by clicking the "Collaborators" link on the left panel.  Collaborators are added by searching for their Zooniverse ID so everyone that will be labelling your data will need an account.

You should also set the project status to "Live" in the visibility interface.  I have left the example project as "Development", because I do not want the example subjects attached to the workflow to be retired.  If the project was set to "Live" images would be retired from the project as soon as 10 people classified an image (10 is the retirement limit in this example).  The project is now good to go, share the link to your project's home page with everyone you want to help you label data or publicise it how ever you want to get even more help.

## Getting your labels ##

Once all your data has been retired from the project, it's time to get your labels.  To do this click on the "Data Exports" link in the left panel of the project builder highlighted with arrow <span style="color:red">**4**</span> in Figure 4.  This will take you to the page shown below.

![Figure 8.](/images/building-an-easily-sharable-interface-to-gather-labels-from-humans/pb_5.png){: .center-image}
*Figure 8. Data Exports interface.*

Click on the "Request new workflow classification export", select the workflow your want a classification export for if you have more than one.  Also click the "Request new subject export". Now, wait for emails with links to the data exports. A clickable link will also appear beside these buttons when they are ready.  Depending on how many classifications have been made on your project it may take a while for the link to become available.  For example, the project I run ([Supernova Hunters](https://www.zooniverse.org/projects/dwright04/supernova-hunters)) has received over 4 million classifications and it can take several hours for the export to be generated.

The files that are generated are [csv](https://en.wikipedia.org/wiki/Comma-separated_values) with embedded [json](https://en.wikipedia.org/wiki/JSON).  This can be a little tricky to parse.  In python be sure to use the [csv package](https://docs.python.org/3/library/csv.html) and something like the [ujson package](https://pypi.org/project/ujson/) which will make life a whole lot easier.  The files contains lots of metadata that you can mostly ignore.  In the workflow classification export you will be most interested in the 'user_name', 'annotations' and 'subject_ids'.  The 'user_name' lets you know who made the classification, the annotation contains their response to the task ('Yes' or 'No' in our example) and the subject_id allows you to link each classification back to the individual image file.  The mapping of subject_id to image file name will be in the subject export you requested along with the classification export.  Alternatively, if you include the image file name as metadata when generating your subject sets then you don't need to bother with the subject export and the metadata is included in the metadata column of the classification export.

The only problem left now is that, if you crowdsourced your labels, each image has multiple classifications.  These need to aggregated into a single label or score for each image.  The easiest way to get a label is to take the majority vote.  To get a score calculate the vote fraction for each class.  That is, of all the users who classified an image, what fraction of them returned each label.  This produces a score, which can be useful to help identify difficult to classify images and can be turned into a hard label by taking the argmax.  There are lots of more sophisticated appraoches you could take (check out our paper ["A transient search using combined human and machine classifications"](https://academic.oup.com/mnras/article/472/2/1315/3979473) for some ideas), but these are a good place to start.

## And finally ... ##

I have also built a drawing workflow into the project called "Where and how many?" so you can see how easy it is to set that up.  The idea would be that annotations from this workflow could be used to train an [RCNN](https://cs.stanford.edu/people/karpathy/rcnn/)-type network.

In order to see how this project is set up in the project builder, you will need to have a Zooniverse account.  Then message me with your Zooniverse username and let me know that you would like to access the template.  The best way to do this is by leaving a message in the [Talk forum](https://www.zooniverse.org/projects/dwright04/city-of-peacetopia-ornithophobia-project/talk).  Otherwise, just get stuck into building your own project as the process is very intuitive after a little bit of digging around.  I've tried to structure this tutorial to avoid some of the "gotchas" I see when people try to use the Project builder for the first time.  But if you do run into trouble you can leave me a message in the project forum, or search for answers and ask for help in the [Zooniverse Talk forums](https://www.zooniverse.org/talk) where there is a [board specifically for project building](https://www.zooniverse.org/talk/18).

I hope you found this useful and it comes in handy next time you need to gather some human labels.
