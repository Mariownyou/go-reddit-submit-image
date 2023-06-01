# go-reddit-uploader: Upload media files to Reddit using the platform's native API. Supports images, videos, or GIFs


## Installation

```bash
go get -u github.com/mariownyou/go-reddit-uploader
```

## Usage

```golang
package main

import (
    "fmt"
    "github.com/mariownyou/go-reddit-uploader"
)

func main() {
    // Create a new uploader
    uploader := reddit_uploader.NewRedditUplaoderClient("username", "password", "client_id", "client_secret")

    // Read the file
    file, _ := os.ReadFile("path/to/file.jpg")

    // Set up the post
    post := reddit_uploader.SubmitParams{
        Subreddit: "subreddit",
        Title: "title",
    }

    response, err := uploader.SubmitImage(post, file, "image.jpg")
    if err != nil {
        panic(err)
    }

    fmt.Println(response)
}
```
