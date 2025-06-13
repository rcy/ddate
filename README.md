# ddate

ddate is a Go package for working with Discordian dates

## Usage

```bash
go get github.com/rcy/ddate
```

```go
package main

import (
	"fmt"
	"time"

	"github.com/rcy/ddate"
)

func main() {
	now := time.Now()
	discordian := ddate.FromTime(now)

	// format with holydays
	fmt.Println(discordian.Format(true))

	// format without holydays
	fmt.Println(discordian.Format(false))

	// compare seasons
	if discordian.Season == ddate.TheAftermath {
		fmt.Println("All the King's Horses and All the King's Men Couldn't put Humpty back together again.")
	}

	// compare weekdays
	if discordian.WeekDay == ddate.PricklePrickle {
		fmt.Println("Hail Eris, Goddess of the days! Sniff me on this Pungenday! Be sure I whiff suitably, like a mangy badger's arse after a long sauna! Whoof!")
	}

	// see if it is St. Tib's Day
	if discordian.HolyDay == ddate.StTibsDay {
		fmt.Println("Happy Birthday to me")
	}
}
```
