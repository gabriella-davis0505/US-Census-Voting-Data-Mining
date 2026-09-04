# Data

This folder contains the datasets used in the US Census and 2020 Presidential Election data-mining project.

## Included Files

### `Attribute_Values.csv`

Lookup information used to decode and label coded attributes in the census dataset.

The coursework used this file when preparing variables such as:

- state;
- education;
- occupation;
- place of birth;
- marital status; and
- other categorical census attributes.

---

### `voting_2020.csv`

2020 US Presidential election results by state.

The dataset contains information including:

- state;
- candidate;
- political party;
- candidate votes;
- total votes; and
- simplified party classification.

This dataset was merged with aggregated census information during the geographic election analysis.

---

## Excluded File

### `Census_Data.csv`

This is the main census dataset used throughout the project.

It contains approximately 1.66 million records and includes variables such as:

- age;
- class of worker;
- education;
- marital status;
- occupation;
- place of birth;
- hours worked;
- sex;
- race;
- state; and
- income.

The file is approximately 94 MB and is not stored directly in this repository due to its size.

The original file has been retained locally.

---

## Geographic Data

A separate dataset containing longitude and latitude information for US states was also used during the mapping analysis.

This was merged with the census and election data using the state field before producing geographic visualisations in Orange.

The original coordinate file is not currently included in this repository.
