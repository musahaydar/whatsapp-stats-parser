# WhatsApp Stats Parser

This script prints stats about a WhatsApp chat. Currently, it outputs the number of messages sent and the number of unique senders after a target date.

## Usage

First, you'll need an exported WhatsApp chat. WhatsApp has an "export chat" feature built in, but it's limited in the number of messages it can export. Exporting without media will increase the number of messages included in the file. Save this `.txt` file in the same directory as this script.

Then, run the following command:

```
./parser --chat <chat_file> --start_date <date>
```

The arguments are as follows:

- `<chat>` is the exported WhatsApp chat file as a `.txt`
- `<date>` is the target start date, after which statistics will be collected. Note that at this time, the date must be formatted as `m/dd/yy`. If the statistics are returned all zeroes, ensure the date is formatted exactly as it appears in the chat file