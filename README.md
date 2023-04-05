# LangChain-chatwithcsv_irisdataset
This script reads data from a CSV file and creates an agent to answer questions about the data using OpenAI's language model. The data used in this example is the Iris dataset, which is a popular dataset in machine learning and consists of measurements of the sepal and petal sizes of three different species of the iris flower.

The script first installs the required libraries and sets the OpenAI API key as an environment variable. It then reads the Iris dataset from a CSV file using pandas and prints the first few rows of the dataset to the console.

The script then creates an agent using the `create_csv_agent()` function from the `langchain.agents` module, which takes an OpenAI language model and a CSV file as inputs. The agent is used to answer questions about the dataset using natural language.

## Installation
To run this script, you will need to have the following libraries installed:

 - pandas
 - langchain
 - openai

These libraries can be installed using pip:

    !pip -q install pandas langchain openai

### Usage
To use this script, you will need to have an OpenAI API key. You can get an API key by creating an account on the OpenAI website.

Once you have an API key, set it as an environment variable in the notebook or script before running the code:

    import os
    
    os.environ["OPENAI_API_KEY"] = "sk-PLACEYOUROWNAPI"

Next, run the following code to read the Iris dataset from a CSV file:

    import pandas as pd
    
    df = pd.read_csv('/path/to/iris.csv')
    
    df.head()

Replace '/path/to/iris.csv' with the path to your own CSV file.

Finally, create an agent using the following code:

    from langchain.agents import create_csv_agent
    from langchain.llms import OpenAI
    
    agent = create_csv_agent(
        OpenAI(temperature=0), 
        '/path/to/iris.csv', 
        verbose=True
    )

You can now use the agent to answer questions about the dataset. For example:

 - `agent('What is the average sepal length for each species?')`

This will return a string containing the answer to the question. The verbose parameter in the create_csv_agent() function controls whether or not debugging information is printed to the console.


## Examples 

- Example 1

![example 1](https://github.com/tolgakurtuluss/LangChain_chatwithcsv_irisdataset/blob/c0cf0f8b8eff7fe37ca28b6d67194b471c39dc6a/example1.PNG)

- Example 2

![example 2](https://github.com/tolgakurtuluss/LangChain_chatwithcsv_irisdataset/blob/c0cf0f8b8eff7fe37ca28b6d67194b471c39dc6a/example2.PNG)

- Example 3

![example 3](https://github.com/tolgakurtuluss/LangChain_chatwithcsv_irisdataset/blob/c0cf0f8b8eff7fe37ca28b6d67194b471c39dc6a/example3.PNG)

## Conclusion
This script demonstrates how to use OpenAI's language model to answer questions about data in a CSV file. By creating an agent using the create_csv_agent() function from the langchain.agents module, you can quickly and easily generate natural language responses to questions about your data.
