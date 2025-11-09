# Tibble-Style Printing for data.table

## Usage

Enable tibble-style printing with a single option:

```r
library(data.table)

# Enable tibble-style printing
options(datatable.print.tibble = TRUE)

DT <- data.table(
  id = 1:100,
  name = paste0("User_", 1:100),
  value = rnorm(100)
)

print(DT)
# Output:
# # A data.table: 100 × 3
#       id name       value
#    <int> <chr>      <dbl>
#  1     1 User_1    0.5855
#  2     2 User_2   -1.2345
#  ...

# Disable (back to standard data.table printing)
options(datatable.print.tibble = FALSE)
print(DT)
```

## Requirements

- The `tibble` package must be installed
- If tibble is not available, a warning is shown and standard printing is used

## Notes

- Only affects display, not the actual data.table object
- All data.table functionality remains unchanged
- Temporary tibble object is automatically cleaned up after printing
