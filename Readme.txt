1. Explanation of the Process to be Automated
The process to be automated through the use of an RPA is called "Cryptocurrency Risk Report". Cryptocurrency Risk Report".
On a daily basis, the company secretary must inform by e-mail to his boss about the risk of buying certain cryptocurrencies. his boss about the risk of buying certain cryptocurrencies.
To do so, the secretary enters a website from where he/she extracts all the information in a table format. in table format.
Once the data has been copied from the website, the secretary pastes the data into excel and evaluates, based on the variation of the last 7 days, whether or not it is risky to invest in each cryptocurrency. cryptocurrency. The risk level for each cryptocurrency will be low if the percentage variation is greater than 0". percentage variation is greater than 0", or a high risk if the variation is less than 0. The final conclusion will be added in the column "Investment_Advice (Risk Level)".
Once the excel with all the relevant information is ready, it is transformed into PDF and then attached in an email that the secretary must send every day to his boss, thus ending the process.

3. Solution.
In order to streamline the process of preparing the "Cryptocurrency Risk Report" and to reduce the workload of the company secretary, it was decided to
Cryptocurrency Risk Report" and reduce the workload of the company secretary, the decision was made to automate this task by means of an RPA solution.
This automation of the process by means of RPA will be carried out with the tool provided by Uipath, Uipath Studio X.
First of all, a Flowchart has been created that includes the entire workflow of the "Report" process.
that collects the "Crypto Risk Report" process.
This workflow is divided into three specific workflows:
- Main: It collects all the sequence of activities used for the extraction of the information in table format from the
of the information in table format from the website, creation of the Excel table with the data and the
Excel table with said data and with the result of the risk assessment of the investment in each of the
the investment risk assessment for each of the cryptocurrencies, which will be added in a new column.
column.
- Transform Excel to PDF: As its name indicates, it includes the
the activity of transforming the Excel file created to a PDF file that will be
file that will later be attached to the email sent to the boss.
- Sending the report: Once the PDF file with the data has been obtained, the information will be
Once the PDF with the data has been obtained, the information will be sent via Gmail to the boss's email.
As mentioned above, the "Main" workflow contains the sequence of activities responsible for the
of activities in charge of extracting and processing the information.
This sequence starts with the opening or creation of the Excel "Data" and then with the extraction of the information.
Activity 3" and subsequently with the extraction of the information in table format from the website
from the website https://es.investing.com/crypto/currencies
This extracted information will then be pasted into the Excel "Data
Activity 3" Excel.
In order to analyse the level of risk of each cryptocurrency, a sequence will be carried out in which the following will be read in a table format
a sequence in which each of the rows of Excel will be read and by means of an
if-else condition will be used to decide whether the cryptocurrency has a High or Low risk level.
A cryptocurrency will be considered to have a high risk level when
variability in the last 7 days has been less than 0. In this case, the value "High" will be written in the "Risk" column of Excel.
Conversely, if its variability over the last 7 days has been positive, its risk level is considered to be low.
considered to have a low level of risk and in the "Risk" column of the Excel spreadsheet the value "Low" shall be entered.
the value "Low" will be entered in the "Risk" column of the Excel spreadsheet.
And once this conversion has been carried out, we perform the loop for each row of the table, in which we save the value of the
in which we save the value of the cell in a System.double variable in order to compare it with the value of the cell in the table.
in order to be able to compare it with the value we took to evaluate the risk, in this case 0.00.
Once the analysis has been carried out, in the workflow "Transform Excel to PDF" the Excel "Data Activity 3" will be exported to PDF format.
Finally, in the workflow "Send report" an email will be sent to the boss via Gmail with the PDF file created.
with the PDF file created, as well as a summary table with the data obtained and the following text data obtained and the following text:
"Hello, along with greetings
I am sending the daily Cryptocurrency risk report.
{{CryptoReport}}
It is also attached in PDF format.

