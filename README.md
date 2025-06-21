# Disco Date

Disco Date is a Go package for working with Discordian dates

## Usage

```bash
go get github.com/rcy/disco
```

```go
package main

import (
	"fmt"
	"time"

	"github.com/rcy/disco"
)

func main() {
	now := time.Now()
	date := disco.FromTime(now)

	// format with holydays
	fmt.Println(date.Format(true))

	// format without holydays
	fmt.Println(date.Format(false))

	// compare seasons
	if date.Season == disco.TheAftermath {
		fmt.Println("All the King's Horses and All the King's Men Couldn't put Humpty back together again.")
	}

	// compare weekdays
	if date.WeekDay == disco.PricklePrickle {
		fmt.Println("Hail Eris, Goddess of the days! Sniff me on this Pungenday! Be sure I whiff suitably, like a mangy badger's arse after a long sauna! Whoof!")
	}

	// see if it is St. Tib's Day
	if date.HolyDay == disco.StTibsDay {
		fmt.Println("Happy Birthday to me")
	}
}
```
