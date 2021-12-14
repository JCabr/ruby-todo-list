# How to find an Item / PO / Delivery / Docktag

See what information you have, and go to the following step:

```
UPC                 --> Step 1
ITEM NUMBER         --> Step 
PO NUMBER           --> Step 
DELIVERY NUMBER     --> Step 
```

1) Go to `MQUN` and enter the UPC
2) A list of item numbers should come up <sup>1</sup>, look at the following
   to get the best item number:
    - The pack; if the item number does not have the right pack, don't use it.
        - Look at the `VNPK` and the `WHPK`; the `VNPK` is the total amount
          of items in the box, and the `WHPK` is the amount of items inside
          any inner containers in the box (called "picks")
        - As an example, a pack of `12 VNPK / 4 WHPK` (or `12/4`) has
          12 inner items, with 3 inner picks containing 4 items inside
    - Any numbers in the `XREF` section on the right; an `XREF` (or
      cross-reference) is an item number linked to another
        - If the item number has the right pack, you can try the `XREF`
          number too
        - Try the `XREF` number first, it usually is `XREF`-ed for a reason
          and would work before the number it is referenced to
3) Once you find a number with a right pack, try entering it into `ITPO`
4) When in `ITPO` put the number, press `[TAB]` to move along the information
   fields and put in what you need
   - Generally, a common useful setup is:

        | Field       | Setting | Description                                 |
        |-------------|---------|---------------------------------------------|
        | `PO-ACTIVE` | `N`     | Show all POs, active or not                 |
        | `HAS-OPEN`  | `Y`     | Show POs that seem to have boxes to receive |
        | `WHSE`      | `6031`  | 6031 is the Walmart DC we work at           |

5) When you have filled in the fields, press `[ENTER]`