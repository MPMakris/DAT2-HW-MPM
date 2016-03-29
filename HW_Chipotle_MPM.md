#Command Line Chipotle HW
##Michael Makris
##DAT2 - 3/28/16

######Question 1:
Each column in the file is a gives information on a particular aspect of an item within an order. "order_id" identifies the order that the item is a part of. "quantity" identifies how many units of each item were in that order. "item name" is the menu name of the item ordered. "choice_description" provides information where the item ordered can vary by customer preference, like soda choice or ingredients in a burrito. "item_price" shows the price for the entire line (accounting for quantity), and varies based on the "choice_description" value for the item.

Each row in the file represents unique items that are part of an order.

_Code Used:_

```$ head chipotle.tsv```

```$ tail chipotle.tsv```

######Question 2:
There appear to be 1834 orders in the record.

_Code Used:_

```$ wc chipotle.tsv```

######Question 3:
There are 4,623 lines in the file.

_Code Used:_

```$ wc chipotle.tsv```

######Question 4:

The Chicken Burrito is appears in more lines in the file than the Steak Burrito, suggesting it is more popular. (553 to 368)

_Code Used:_

```$ grep "Steak Burrito" chipotle.tsv | wc```

```$ grep "Chicken Burrito" chipotle.tsv | wc```

(The first output for both commands indicates the number of lines the burrito appears within.)

######Question 5:

Black Beans appear in more lines in the file than Pinto Beans, suggesting they are more popular. (282 to 105)

_Code Used:_

```$ grep "Chicken Burrito" chipotle.tsv | grep -i "black beans" | wc```

```$ grep "Chicken Burrito" chipotle.tsv | grep -i "pinto beans" | wc```

(The first output for both commands indicates the number of lines the bean variety appears within.)

###### Question 6:

There are 13 \*.tsv and \*.csv files in the **DAT8** repo:

* ./data/airlines.csv
* ./data/bank-additional.csv
* ./data/bikeshare.csv
* ./data/chipotle.tsv
* ./data/drinks.csv
* ./data/hitters.csv
* ./data/imdb_1000.csv
* ./data/sms.tsv
* ./data/titanic.csv
* ./data/ufo.csv
* ./data/vehicles_test.csv
* ./data/vehicles_train.csv
* ./data/yelp.csv



_Code Used:_

```$ find . -name *.?sv```

```$ find . -name *.?sv | wc```

###### Question 7:

The word _dictionary_ appears 81 times in the **DAT8** repo.

_Code Used:_

```$ grep -ir dictionary . | wc```

######Question 8: (Optional)

The most commonly ordered Canned Soda is a Coca Cola. Below is a list of the Canned Sodas ranked by the number of lines they appear in.

1. 26 [Coca Cola]
* 18 [Dr. Pepper]
* 17 [Sprite]
* 15 [Mountain Dew]
* 15 [Diet Coke]
* 13 [Diet Dr. Pepper]

_Code Used:_

```$ grep -i "canned soda" chipotle.tsv | cut -f4 | sort | uniq -c | sort -r```