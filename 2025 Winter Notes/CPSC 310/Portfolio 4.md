***
```ts
function dayOfYear(month: number, dayOfMonth: number, year: number): number {
    if (month === 2) {
        dayOfMonth += 31;
    } else if (month === 3) {
        dayOfMonth += 59;
    } else if (month === 4) {
        dayOfMonth += 90;
    } else if (month === 5) {
        dayOfMonth += 31 + 28 + 31 + 30;
    } else if (month === 6) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31;
    } else if (month === 7) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31 + 30;
    } else if (month === 8) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31 + 30 + 31;
    } else if (month === 9) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31 + 30 + 31 + 31;
    } else if (month === 10) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31 + 30 + 31 + 31 + 30;
    } else if (month === 11) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31 + 30 + 31 + 31 + 30 + 31;
    } else if (month === 12) {
        dayOfMonth += 31 + 28 + 31 + 30 + 31 + 30 + 31 + 31 + 30 + 31 + 31;
    }
    return dayOfMonth;
}
```
* For December the added value is incorrect as November is 30 days instead of 31.
* Year is passed through and never used (should be used for leap years)
* Inconsistent adding
* Hard to read with this many else if statements