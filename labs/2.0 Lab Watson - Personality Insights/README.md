![](.//media/image1.png)

# 2.0 Lab Watson - Personality Insights

Objective
=========

In the first part on the lab, you will access a Personality Insights quick demo so as to understand the Personality Insights service and its use in an application. With this service you can gain insight into how
and why people think, act, and feel the way they do. This service applies linguistic analytics and personality theory to infer attributes from a person\'s unstructured text.

In the second part of the lab, you will create a Watson Personality Insights service and then you will learn how to call it through cURL commands.

Personality Insights quick demo
===============================

You can access the Personality Insights quick demo at the following url:

<https://personality-insights-demo.ng.bluemix.net/>

![](.//media/image2.png)

Personality Insights service allows to gain insight into how and why people think, act, and feel the way they do. This service applies linguistic analytics and personality theory to infer attributes from a
person\'s unstructured text.

The quick demo application allows to analyze text from three sources:

-   Tweets and replies from several people (Oprah Winfrey, LeBron James, Don Francisco, Pope Francis, Mohamed Aboutrika, Sefat Farid Yu Darvish and Sandara Park)

-   Text from several people (Barack Obama, Gandhi and Natsume Soseki) or your own text (more than 100 words)

-   Your own tweets and replies

For tweets and replies analysis, first select a twitter account and click on the Analyze button.

![](.//media/image3.png)

You get the results of the analysis in the Output section.

First output is a summary of the personality.

![](.//media/image4.png)

On the right, you can see the consumption preferences.

The Personality Insights service infers consumption preferences based on the results of its personality profile for the author of the input text. From existing literature, IBM identified 104 consumption preferences that have proved to be correlated with personality. These include preferences that are related to shopping, movies, music, and other categories. IBM then created a psychometric survey to assess an
individual\'s inclination for each consumption behavior.

IBM obtained responses to its survey from about 600 individuals for whom it also had Twitter data (more than 200 self-authored tweets for each user). IBM submitted the tweets to the service to gather a personality profile for each individual. It then built a classifier for each consumption preference, where the input feature set was the personality information.

For inclusion with the service, IBM selected only those consumption preferences for which personality-based classification performed at least 9 percent better than random classification. Of the original 104
preferences, 42 satisfied this criterion and are exposed as consumption preferences by the service.

Here is the list of the consumption preferences returned by the service:

-   Shopping preferences: Shopping preferences indicate the author\'s interest in different types of purchases, the extent to which the author\'s purchasing habits are influenced by different external
    sources, and the author\'s spending habits. This category has 12 preferences.

-   Movie preferences: Movie preferences indicate the author\'s interest in different types of movies. This category has 10 preferences.

-   Music preferences: Music preferences indicate the author\'s interest in different types of music and whether the author enjoys playing music. This category has nine preferences.

-   Reading and learning preferences: Reading and learning preferences indicate the author\'s likelihood to read, the author\'s motivation for reading, and the types of content the author enjoys reading.
    This category has five preferences.

-   Health and activities preferences: Health and activity preferences indicate the author\'s interest in healthy foods and physical activity. This category has three preferences.

-   Entrepreneurship preferences: Entrepreneurship preferences indicate the author\'s interest in starting a business. This category has one preference.

-   Environmental concern preferences: Environmental concern preferences indicate the author\'s interest in the environment. This category has one preference.

-   Volunteering preferences: Volunteering preferences indicate the author\'s interest in volunteering for social causes. This category has one preference.

Here is a table summarizing the consumption preferences:

| Shopping   preferences              | Likely to be   sensitive to ownership cost when buying automobiles |
| ----------------------------------- | ------------------------------------------------------------ |
|                                     | Likely to   prefer safety when buying automobiles            |
|                                     | Likely to   prefer quality when buying clothes               |
|                                     | Likely to   prefer style when buying clothes                 |
|                                     | Likely to   prefer comfort when buying clothes               |
|                                     | Likely to be   influenced by brand name when making product purchases |
|                                     | Likely to be   influenced by product utility when making product purchases |
|                                     | Likely to be   influenced by online ads when making product purchases |
|                                     | Likely to be   influenced by social media when making product purchases |
|                                     | Likely to be   influenced by family when making product purchases |
|                                     | Likely to   indulge in spur of the moment purchases          |
|                                     | Likely to   prefer using credit cards for shopping           |
| Movie   preferences                 | Likely to like   romance movies                              |
|                                     | Likely to like   adventure movies                            |
|                                     | Likely to like   horror movies                               |
|                                     | Likely to like   musical movies                              |
|                                     | Likely to like   historical movies                           |
|                                     | Likely to like   science-fiction movies                      |
|                                     | Likely to like   war movies                                  |
|                                     | Likely to like   drama movies                                |
|                                     | Likely to like   action movies                               |
|                                     | Likely to like   documentary movies                          |
| Music   preferences                 | Likely to like   rap music                                   |
|                                     | Likely to like   country music                               |
|                                     | Likely to like   R&B music                                   |
|                                     | Likely to like   hip hop music                               |
|                                     | Likely to   attend live musical events                       |
|                                     | Likely to have   experience playing music                    |
|                                     | Likely to like   Latin music                                 |
|                                     | Likely to like   rock music                                  |
|                                     | Likely to like   classical music                             |
| Reading and   learning preferences  | Likely to read   often                                       |
|                                     | Likely to read   entertainment magazines                     |
|                                     | Likely to read   non-fiction books                           |
|                                     | Likely to read   financial investment books                  |
|                                     | Likely to read   autobiographical books                      |
| Health and   activities preferences | Likely to eat   out frequently                               |
|                                     | Likely to have   a gym membership                            |
|                                     | Likely to like   outdoor activities                          |
| Entrepreneurship   preferences      | Likely to consider   starting a business in next few years   |
| Environmental   concern preferences | Likely to be   concerned about the environment               |
| Volunteering   preferences          | Likely to   volunteer for social causes                      |

Then you can find the models reported by the service:

![](.//media/image5.png)

**Personality**: based on the Big Five model. Big Five is one of the most studied of the personality models that were developed by psychologists Costa and McCrae (1992), and Norman (1963). It is the most
widely used personality model to describe how a person generally engages with the world. The service computes the five dimensions and thirty facets of the model. The dimensions are often referred to by the
mnemonic *OCEAN*, where *O* stands for Openness, *C* for Conscientiousness, *E* for Extraversion, *A* for Agreeableness, and *N* for Neuroticism. (Because the term Neuroticism can have a specific
clinical meaning, the service presents such insights under the more generally applicable heading Emotional range.)

For each dimension you can get details by clicking on the arrow sign next to it.

![](.//media/image6.png)

**Consumer Needs**: Needs are an important aspect of human behavior. Research literature suggests that several types of human needs are universal and directly influence consumer behavior (Kotler and Armstrong (2013) and Ford (2005)). The twelve categories of needs that are reported by the service are described in marketing literature as desires that people hope to fulfill when they consider a product or service.

**Values**: Values convey what is most important to an individual. They are "desirable, trans-situational goals, varying in importance, that serve as guiding principles in people\'s lives" (Schwartz, 2006). Schwartz summarizes five features that are common to all values:

1.  Values are beliefs.

2.  Values are a motivational construct.

3.  Values transcend specific actions and situations.

4.  Values guide the selection or evaluation of actions, policies, people, and events.

5.  Values vary by relative importance and can be ranked by importance.

The service computes the five basic human values that were proposed by Schwartz and that were validated in more than twenty countries(Schwartz, 1992).

You can get an explanation of each characteristic simply by hovering over it.

![](.//media/image7.png)

You can get a sunburst visualization by clicking on the "View personality traits in sunburst visualization" link.

![](.//media/image8.png)

Create the Watson Personality Insights service and call it
==========================================================

Log in and create the service
-----------------------------

1.  Navigate to the [IBM Cloud](https://www.ibm.com/cloud/).

2.  Log in to the IBM Cloud.

3.  On the IBM Cloud dashboard, select Catalog from the menu bar.

4.  Enter Personality in Search the catalog.

5.  Click on Personality Insights.

    ![](.//media/image9.png)

6.  Select the Lite plan and click on Create.

7.  You get to the Personality Insights created service dashboard.

    ![](.//media/image10.png)

Copy the credentials to authenticate to your service instance
-------------------------------------------------------------

1.  On the Personality Insights service dashboard page, click on Manage.

2.  On the Manage page, click **Show Credentials** to view your credentials.


    ![](.//media/image11.png)

3.  Copy the API Key and URL values.

Curl command
------------

The examples described in this document use the curl command to call methods of the HTTP interface.

Make sure that you have the curl command installed on your laptop.

If not already installed, install the version for your operating system from [curl.haxx.se](https://curl.haxx.se/)

Install the version that supports the Secure Sockets Layer (SSL) protocol. Make sure to include the installed binary file on your PATH environment variable.

When you enter a command, replace {apikey} and {url} with your actual API key and URL. Omit the braces, which indicate a variable value, from the command.

Send plain text input and receive basic JSON output
---------------------------------------------------

This first example passes the plain text file profile.txt to the POST /v3/profile method and requests a JSON response.

1.  Download the sample file [profile.txt](https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt)

2.  Issue the following command to send the file to the /v3/profile method and request a JSON response.


a.  The Content-Type header specifies that the input is plain text, text/plain. The charset parameter included with the header identifies the character encoding of the input text.

    b.  The Accept header specifies application/json to indicate that JSON output is requested.

c.  Replace {apikey} and {url} with your information.

    d.  Modify {path\_to\_file} to specify the location of the profile.txt file.

Linux version of the command:

```
curl -X POST -u "apikey:{apikey}" --header "Content-Type: text/plain;charset=utf-8" --header "Accept: application/json" --data-binary @{path_to_file}profile.txt "{url}/v3/profile?version=2017-10-13"
```

Windows version of the command:

```
curl -X POST -u "apikey:{apikey}" --header "Content-Type: text/plain;charset=utf-8" --header "Accept: application/json" --data-binary "@{path_to_file}profile.txt" "{url}/v3/profile?version=2017-10-13"
```

The service returns a JSON Profile object that includes basic metadata such as the number of words in the input, the language model with which the input was processed, and any warnings associated with the input.

The profile includes information about the Big Five personality, Needs, and Values characteristics for the author as inferred from the input text. The service reports a percentile, or normalized score, for each
characteristic. The service computes the percentile by comparing the author\'s results with the results from a sample population.

Send JSON input and receive detailed JSON output
------------------------------------------------

In this example, a JSON file is passed to the /v3/profile method, again requesting a JSON response. The example requests consumption preferences and raw scores for a more detailed analysis of the input.

1.  Download the sample file [profile.json](https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json). This file contains a collection of Twitter messages.

2.  Issue the following command to send the file to the /v3/profile method. The example specifies application/json for the Content-Type and Accept headers; the charset parameter is not needed for JSON input. The example sets the consumption\_preferences and raw\_scores query parameters to true.



Linux version of the command:

```
curl -X POST -u "apikey:{apikey}" --header "Content-Type: application/json" --header "Accept: application/json" --data-binary @{path_to_file}profile.json "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
```

Windows version of the command:

```
curl -X POST -u "apikey:{apikey}" --header "Content-Type: application/json" --header "Accept: application/json" --data-binary "@{path_to_file}profile.json" "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
```

The service returns a JSON profile that includes the metadata and characteristics returned with the previous example. For each characteristic, the service also includes a raw\_score, which represents
the author\'s score for the characteristic based solely on the input text, without comparing the results to a sample population.

Because the input content includes timestamps, the service also reports behavioral characteristics. These are temporal characteristics that indicate the percentage of the content items that were created on each
day of the week and hour of the day.

The service also reports scores for its collection of consumption preferences. The scores indicate the author\'s likelihood to prefer different products, services, and activities based on the inferred
characteristics.

Send JSON input and receive detailed CSV output
-----------------------------------------------

This example is similar to the previous one: it passes the same JSON content and requests the same results. But this example specifies text/csv for the Accept header to request the response in
comma-separated values (CSV) format. It uses the \--output option of the curl command to direct the results to a file named profile.csv. The example sets the csv\_headers query parameter to true to request that
column headers be returned with the output.

Issue the following command to send the JSON file to the /v3/profile method. The Content-Type header identifies the input content as application/json, and the Accept header requests CSV output, text/csv:

Linux version of the command:

```
curl -X POST -u "apikey:{apikey}" --header "Content-Type: application/json" --header "Accept: text/csv" --data-binary @{path_to_file}profile.json --output profile.csv "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
```

Windows version of the command :

```
curl -X POST -u "apikey:{apikey}" --header "Content-Type: application/json" --header "Accept: text/csv" --data-binary "@{path_to_file}profile.json" --output profile.csv
"{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
```



Conclusion
==========

In this short lab exercise, you have created a Watson Personality Insights service and you have learned how to call the service's POST /v3/profile method with different types of input and how to request different types of output and output format.
