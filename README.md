----

net.http.handler.gzip: a FileServer that serves gzipped content.

Usage:

```go
import "github.com/blockninja/fileserver"

base := "/path/to/website/static/files"
http.Handle("/static", http.StripPrefix("/static", gzip.FileServer(http.Dir(base))))

```
Usage of http.FileServer can be replaced with gzip.FileServer. A request for <file> serves <file>.gz instead if its modification time is not before the original file's, or if the original does not exist. Serves the original if the request doesn't support the "gzip" encoding. index.html can also be gzipped as a default for directories (index.html.gz).
