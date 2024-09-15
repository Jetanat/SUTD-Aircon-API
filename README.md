# Quick Introduction: 
This is an example plot that tracks aircon balance movement, generated using the Jet_SUTD_Aircon library. This library allows users to manage their aircon credit, retrieve transaction history, and monitor balance trends over time.

![Screenshot](https://github.com/Jetanat/SUTD-Aircon-API/blob/main/plot.png)

# SUTD-Aircon-API
Jet_SUTD_Aircon is a Python API designed to manage SUTD Aircon account services. It enables users to check their Aircon credit balance, review transaction history, and add additional credits seamlessly. <br />

# Jet SUTD Aircon
1.) Context and Purpose <br />
Students residing in the SUTD hostel who wish to use air conditioning typically need to top-up their aircon credit. The instructions for topping up can be found at the following link https://nus-utown.evs.com.sg/SUTD/. This portal allows users to add credit, view their transaction history, and check their current aircon balance. <br />
2.) Challenges <br />
The current system only displays the aircon balance at the moment of inquiry, without providing a detailed balance history. This limitation makes it difficult for users to track their aircon usage over time, such as plotting usage against balance history. Additionally, the portal does not offer a Python API library for programmatically accessing data, meaning users must manually log in, input their credentials, and navigate to "View Meter Credit" to obtain their balance, limiting transaction tracking to only individual usage. <br />
3.) Solution Impact <br />
To address these challenges, I developed a Python API library called Jet SUTD Aircon. This library allows users to manage their aircon credit, retrieve transaction histories, and create a personalized database using a dataframe. Most importantly, it enables users to access and analyze their aircon balance history. By tracking this history, users can better monitor and optimize their aircon credit usage over time. <br />

# Disclaimer (Please read this!!!) 
This software is provided “as-is,” without any warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the creator or contributors be held liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use of other dealings in the software. <br />

# Jetanat License:
1.)	**Acknowledgment**: Users of this software must acknowledge the original author in any academic or public use of the software. This acknowledgment should include the author's name and any applicable copyright notice. <br />
2.)	**Commercial Use**: For any commercial product or service that incorporates this software, the user must obtain explicit permission from the original author before distributing or selling the commercial product. <br />
3.)	**No Charge for Public Use**: The software is provided free of charge for public use and cannot be sold or sublicensed for commercial purposes without the author's permission. <br />
4.)	**No Warranty**: The software is provided "as-is," without any warranties, express or implied. <br />

# Instruction on how to use Jet SUTD Aircon:
## First, make sure that you have the following python libraries installed 
1.)	“Python 3.x.x” (the created project ran on python 3.11) <br />
2.)	“Requests” <br />
3.)	“BeautifulSoup” <br />
4.)	“datetime” <br />
5.)	“pandas” <br />
6.)	“os” <br />

The quick way to check if you have these libraries available is as follows: <br />
`import requests` <br />
`from bs4 import BeautifulSoup` <br />
`import webbrowser` <br />
`from datetime import datetime` <br />
`import pandas as pd` <br />
`import os` <br />

## Second, make sure that in “config.py”, you have entered the AirconID and AirconPW correctly, and make sure that your AirconID and your Aircon password are inside a quotation (“    ”). 
AirconID = `"<your AirconID>"` <br />
AirconPW = `"<your Aircon password>"` <br />

![Screenshot](https://github.com/Jetanat/SUTD-Aircon-API/blob/main/config_file.PNG)

## Third, the only two files you need from my respository are 
1.) `config.py`
2.) `Jet_SUTD_Aircon.pyd`

# The main API in Jet_SUTD_Aircon:
1.)	The declaration of `Jet_SUTD_Aircon(AirconID=AirconID, AirconPW=AirconPW)` is to login to your SUTD aircon account. The parameters `AirconID` and `AirconPW` are your Aircon ID and Password respectively. These parameters shall be stored in `config.py`.  <br />
2.)	A method `get_credit_database()` is to get **“my_aircon_credit_table.csv”** and return the file as dataframe.  <br />
3.)	A method `update_credit()` is to get your current credit balance from the SUTD aircon database and then store your current credit balance to your own database **"my_aircon_credit_table.csv"**.  <br />
4.)	A method `get_transaction_database()` is to get **“my_aircon_transaction_table.csv”** and return the file as dataframe.  <br />
5.)	A method `update_transaction()` is to get your transaction history from the SUTD aircon database and then store your current transaction history to your own database **"my_aircon_transaction_table.csv"**. <br />
6.)	A method `add_aircon_credit(add_amount)` is to submit an amount of dollars you like to pay to top-up your aircon credit. The top-up amount ranges from S$ 10 to S$ 50. After that you will be directed to a bank’s web browser in order to fill out your bank information to pay the school in order to top-up your aircon credit. In my experience, the top-up aircon credit usually available within 24 – 36 hours, but the transaction record is updated in a few minutes.  <br />
![Screenshot](https://github.com/Jetanat/SUTD-Aircon-API/blob/main/BankTransaction.PNG)
