# Disco Date

Disco Date is a Go package for working with Discordian dates

## Usage

```bash
go get github.com/rcy/discodate
```

```go
package main

import (
	"fmt"
	"time"

	"github.com/rcy/discodate"
)

func main() {
	now := time.Now()
	discordian := discodate.FromTime(now)

	// format with holydays
	fmt.Println(discordian.Format(true))

	// format without holydays
	fmt.Println(discordian.Format(false))

	// compare seasons
	if discordian.Season == discodate.TheAftermath {
		fmt.Println("All the King's Horses and All the King's Men Couldn't put Humpty back together again.")
	}

	// compare weekdays
	if discordian.WeekDay == discodate.PricklePrickle {
		fmt.Println("Hail Eris, Goddess of the days! Sniff me on this Pungenday! Be sure I whiff suitably, like a mangy badger's arse after a long sauna! Whoof!")
	}

	// see if it is St. Tib's Day
	if discordian.HolyDay == discodate.StTibsDay {
		fmt.Println("Happy Birthday to me")
	}
}
```
