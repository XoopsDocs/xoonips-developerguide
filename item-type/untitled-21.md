---
description: >-
  Item information is divided into Basic Information and Detail Information as
  shown below.
---

# 2. Item overview

## 1. Basic Information

Information \(fields\) owned by all items regardless of item type is called Basic Information. It has the following items.

* title
* keyword
* comment
* DOI
* Date of the contents of the item \[ [1](https://xoonips.osdn.jp/manuals/itemtype-340/item.html#ftn.id360007) \]
* Create user
* Created date
* last updated
* language

Of these, the system determines the creator, creation date, and last update date. The user cannot be specified.

The system is in charge of part of the registration of Basic Information in the DB, acquisition from the DB, parameter check, and form creation processing. The item type module creator does not need to create these processes. Since it is provided in the form of a function in the common library, it is called and used as needed.

## 2. Detail Information

Refers to item type-specific information that is not included in Basic Information. The item type module handles all Detail Information. The recording method and processing method can be freely determined by the item type.

## 3. Correspondence between Basic Information and Detail Information

As mentioned above, information about one item is managed separately as Basic Information and Detail Information. The item ID exists to take the correspondence between the two. Manage the item type module by associating the item ID given by the system with Detail Information. The system treats Basic Information and Detail Information with the same item ID as one item \( [Fig. 2.1. "Association by Item ID \(Example\)"](https://xoonips.osdn.jp/manuals/itemtype-340/item.html#fig.item.basic-detail.example) \).![Correspondence by item ID \(example\)](https://xoonips.osdn.jp/manuals/itemtype-340/images/relation.gif)

**Figure 2.1. Correspondence by item ID \(example\)**

\[ [1](https://xoonips.osdn.jp/manuals/itemtype-340/item.html#id360007) \] If the item is a paper, specify the publication date of the paper, and if it is a program, specify the release date. What the date means depends on the item type. Some item types do not use the date.

