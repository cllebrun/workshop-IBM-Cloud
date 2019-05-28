![](.//media/image1.png)

# 2.1 Lab Watson - Tone Analyzer

Objective
=========

In the first part on the lab, you will access two Tone Analyzer quick demos so as to understand the Tone Analyzer service and its use in an application.

In the second part of the lab, you will create a Tone Analyzer service and you will then a create a Node-RED application that uses this created service.

Tone Analyzer (General purpose) quick demo
==========================================

You can access the Tone Analyzer General purpose quick demo at the following url:

https://tone-analyzer-demo.ng.bluemix.net/

![](.//media/image2.png){width="6.5in" height="3.65625in"}

Select one of the example (Tweets, Online Review, Email message, Product, Review in French or Your own text) and click on Analyze.

You get the results of the analysis in the Output section.

![](.//media/image3.png){width="6.5in" height="3.65625in"}

Here is a description of the different emotional and language tones:

**Anger**: Anger is evoked due to injustice, conflict, humiliation, negligence, or betrayal. If anger is active, the individual attacks the target, verbally or physically. If anger is passive, the person silently
sulks and feels tension and hostility. (An emotional tone.)

**Fear**: Fear is a response to impending danger. It is a survival mechanism that is triggered as a reaction to some negative stimulus. Fear can be a mild caution or an extreme phobia. (An emotional tone.)

**Joy**: Joy (or happiness) has shades of enjoyment, satisfaction, and pleasure. Joy brings a sense of well-being, inner peace, love, safety, and contentment. (An emotional tone.)

**Sadness**: Sadness indicates a feeling of loss and disadvantage. When a person is quiet, less energetic, and withdrawn, it can be inferred that they feel sadness. (An emotional tone.)

**Analytical**: An analytical tone indicates a person\'s reasoning and analytical attitude about things. An analytical person might be perceived as intellectual, rational, systematic, emotionless, or
impersonal. (A language tone.)

**Confident**: A confident tone indicates a person\'s degree of certainty. A confident person might be perceived as assured, collected, hopeful, or egotistical. (A language tone.)

**Tentative**: A tentative tone indicates a person\'s degree of inhibition. A tentative person might be perceived as questionable, doubtful, or debatable. (A language tone.)

There is an analysis at the document level and an analysis at the sentence level.

Tone Analyzer (Customer engagement) quick demo
==============================================

You can access the Tone Analyzer Customer engagement quick demo at the following url:

<https://customer-engagement-demo.ng.bluemix.net/>

![](.//media/image4.png){width="6.5in" height="3.65625in"}

You can use the Tone Analyzer for Customer Engagement endpoint to monitor customer support conversations. Escalate customer conversations when they turn sour, or find opportunities to improve customer service scripts, dialogs and customer journeys. Tones detected with this
endpoint include frustrated, sad, satisfied, excited, polite, impolite and sympathetic.

This service uses linguistic analysis to detect joy, fear, sadness, anger, analytical, confident and tentative tones found in text.

Select a language (English or French) and have a look at the different tones found during the conversation.

You can enter your own sentences and click on Reply to see the results of the Tone Analyzer service.

Create the Watson Tone Analyzer service and call it
===================================================

Log in and create the service
-----------------------------

1.  Navigate to the [IBM Cloud](https://www.ibm.com/cloud/).

2.  Log in to the IBM Cloud.

3.  On the IBM Cloud dashboard, select Catalog from the menu bar.

4.  Enter Tone in Search the catalog.

5.  Click on Tone Analyzer.

> ![](.//media/image5.png){width="6.5in" height="3.65625in"}

6.  Select the Lite plan and click on Create.

7.  You get to the Tone Analyzer created service dashboard.

> ![](.//media/image6.png){width="6.5in" height="3.65625in"}

Copy the credentials to authenticate to your service instance
-------------------------------------------------------------

1.  On the Tone Analyzer service dashboard page, click on Manage.

2.  On the Manage page, click **Show Credentials** to view your credentials.

![](.//media/image7.png){width="6.5in" height="3.65625in"}

3.  Copy the API Key and URL values.

Node-RED
--------

In this lab we will use Node-RED to call the Tone Analyzer service.

1.  On the IBM Cloud dashboard, select Catalog from the menu bar.

2.  Enter Node-RED in Search the catalog.

3.  Click on Node-RED Starter.

![](.//media/image8.png){width="6.5in" height="3.65625in"}

4.  Give a name for the application, select the Default plan and click on Create.

![](.//media/image9.png){width="6.5in" height="3.65625in"}

5.  Wait for your application to start and then click on Visit App URL.

    ![](.//media/image10.png){width="6.5in" height="3.65625in"}

6.  Follow the instructions to secure your Node-RED application.

    ![](.//media/image11.png){width="6.5in" height="3.65625in"}

7.  Click on Go to your Node-RED editor

Use Tone Analyzer inside Node-RED
---------------------------------

1.  Drap and drop the Tone Analyzer node on the palette.

    ![](.//media/image12.png){width="6.5in" height="3.65625in"}

2.  Double-click on the node to edit its properties.

    ![](.//media/image13.png){width="6.5in" height="3.65625in"}

3.  Put the API key of the Tone Analyzer service you created previously, deselect Use Default Service Endpoint and enter the Service Endpoint of the Tone Analyzer service, select Multiple Tones for the
    version\_date field.

    ![](.//media/image14.png){width="6.5in" height="3.65625in"}

4.  Click on Done.

5.  Drag and drop an inject node and a debug node from the palette.

    ![](.//media/image15.png){width="6.5in" height="3.65625in"}

6.  Wire the nodes together.

    ![](.//media/image16.png){width="6.5in" height="3.65625in"}

7.  Double-click the timestamp node to edit its properties.

8.  For the Payload select String and enter the sentences that you want to be analyzed. Here is an example that you can use: "Team, I know that times are tough! Product sales have been disappointing for the
    past three quarters. We have a competitive product, but we need to do a better job of selling it!"

    ![](.//media/image17.png){width="6.5in" height="3.65625in"}

9.  Click on Done.

10. Double click the msg.payload node to edit its properties.

11. Replace the word payload by the word response.

    ![](.//media/image18.png){width="6.5in" height="3.65625in"}

12. Click on Done.

13. Click on Deploy.

> ![](.//media/image19.png){width="6.5in" height="3.65625in"}

14. You should get a Successfully deployed message.

15. Run the flow by clicking on the left of the inject node.

16. You should get a Successfully injected message.

17. You can visualize the response by clicking on the Debug messages icon on the top right.

> ![](.//media/image20.png){width="6.5in" height="3.65625in"}

18. You can see the output of the Tone Analyzer service in the response object.

![](.//media/image21.png){width="6.5in" height="3.65625in"}

The service returns a JSON object that always contains a document\_tone field. This field contains an object that provides the analysis of the full input document. It contains a single field, tones, that provides
the results of the analysis for each qualifying tone of the document. If the sentences parameter of the request is omitted or set to true, the response also includes a sentences\_tone field. This field contains an
array of objects, each of which provides the following information for a different sentence from the input content:

-   sentence\_id (integer) provides the unique identifier for the sentence. The first sentence has ID 0, and the ID of each subsequent sentence is incremented by one.
-   text (string) provides the text of the sentence.

-   tones provides the results of the analysis for each qualifying tone of the sentence.

19. Feel free to test your own text by modifying the payload message in the inject node.

Conclusion
==========

In this short lab exercise, you have created a Tone Analyzer service and you have learned how to call this service from a Node-RED application.
