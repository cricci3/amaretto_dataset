# Amaretto Dataset - A Synthetic Capital Market Dataset

This is the official repository for the Amaretto dataset in collaboration with Politecnico di Milano (Italy) and Napier Limited (UK).

To cite the Amaretto dataset, please use the following BibTeX and the DOI: `TBD`

```
@article{ReCAN2020, 
  title     = {Amaretto: An Active Learning Framework for Money Laundering Detection},
  author    = {Labanca, Danilo and Primerano, Luca and Markland-Montgomery, Marcus and Polino, Mario and Carminati, Michele and Zanero, Stefano}, 
  year      = {2022}, 
  volume    = {TBD},
  pages     = {TBD},
  journal   = {IEEE Access},
  doi       = {TBD},
} 
```
## Authors
- Danilo Labanca (danilo [dot] labanca [at] mail  [at] polimi [dot] it) <sup>P</sup>
- Luca Primerano (luca [dot] primerano [dot] uk [at] gmail [dot] com) 
- Marcus Markland-Montgomery (markus [dot] markland [at] napier [dot] ai) <sup>N</sup>
- Mario Polino (mario [dot] polino [at] polimi [dot] it) <sup>P</sup>
- Michele Carminati (michele [dot] carminati [at] polimi [dot] it) <sup>P</sup>
- Stefano Zanero (stefano [dot] zanero [at] polimi [dot] it) <sup>P</sup>

## Affiliations
 <sup>N</sup> Authors are with Napier Technologies Limited, London, UK
 
 <sup>P</sup> Authors are with the Dipartimento di Elettronica, Informazione e Bioingegneria, Politecnico di Milano, Italy
 
 ## Description
 
The data combines more than 10,000 parameters extrapolated from real market data. The dataset consists of 29,704,090 transactions executed by 400 end clients buying and selling specific securities in a specific market. 
Circa 90\% of the users made at least 50,000 transactions while 10\% of the users performed circa 400,000, which means that 10\% of the clients executed almost 50\% of the transactions. 98.43\% of the transactions have an amount less than 1M USD, and 40\% of them have an amount less than 10K USD. Data covers 60 days divided into 12 weeks (a week is composed of 5 days. Saturdays and Sundays are not included because during the weekend markets are closed). Transactions are evenly distributed between the 12 weeks, and most of them are executed during market opening hours, while only a small percentage is executed during the early morning hours and at the end of the day. 

|Total Transactions| Legitimate Transactions (L) | Anomalous Transactions (T) | Ratio (A/T) | Number of Attributes | Number of Originators |
|------------------|-----------------------------|----------------------------|-------------|----------------------|-----------------------|
|    29,704,090    |      29,622,822             |          81,262            |     0.27%   |         12           |          40           |

Key fields contained in the data include the transaction amount, the product class (There are 17 different products, representing the main product traded in the capital market -- e.g., Equity, Fixed Income), product type (e.g., cash equity, future equity, bond), time field, currency, market. Within the data, it is not possible to identify any specific statistical distributions in any key field.
 
\subsection{Synthetic Anomalies Overview}

Financial datasets are known to be extremely unbalanced, usually containing from 0.1% to 1 % of anomalous transactions (#1). Therefore, to replicate real-world scenarios, we set the number of anomalies to less than 1 % of the data. As part of this dataset, we generated five classes of anomalies based on examples of suspicious patterns suggested by FATF (#2), an inter-governmental body that promotes effective implementation of legal, regulatory, and operational measures for combating money laundering. Anomalous transactions will follow the same trend to reinforce the concept that anomalous transactions are well hidden in the dataset. Below, we describe the classes of anomalies injected in the dataset. 

- ***Small but highly frequent transactions generated within a short timeframe***: A pattern that contains multiple transactions below applicable reporting thresholds. 
- ***Transactions with rounded normalized amounts bought or sold within an account***: It is unusual for transactions in capital markets to have rounded amounts (unless they occur in markets where foreign exchange conversion causes rounding errors). 
- ***Security bought or sold at an unusual time***: It is unusual for clients to trade specific securities outside of a specific timeframe (for example, outside of the opening and closing times of a stock exchange). 
- ***Large asset withdrawal***: A sudden spike in transaction amount withdrawn from an account or transferred out, which deviates from the previous transactional activity and is absent any commercial rationale or related corporate action event. 
- ***An unusually large amount of collateral transferred in and out of an account within a short period of time***: This behavior is unusual as a client would not be able to invest by simply trading collateral, or at least such a strategy would be unusual.

## Bibliography
1.  M. Carminati, M. Polino, A. Continella, A. Lanzi, F. Maggi, and S. Zanero, “Security evaluation of a banking fraud analysis system,” ACM Transactions on Privacy and Security (TOPS), vol. 21, no. 3, pp. 1–31, 2018
2. FATF, “Guidance for a risk-based approach: securities sector,”https://www.fatf-gafi.org/media/fatf/documents/recommendations/pdfs/RBA-Securities-Sector.pdf, 2018
