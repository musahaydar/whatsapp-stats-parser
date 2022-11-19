# WhatsApp Stats Parser

This script prints stats about a WhatsApp chat. Currently, it outputs the number of messages sent and the number of unique senders after a target date.

## Usage

First, you'll need an exported WhatsApp chat. WhatsApp has an "export chat" feature built in, but it's limited in the number of messages it can export. Exporting without media will increase the number of messages included in the file. Save this `.txt` file in the same directory as this script.

Then, run the following command:

```
./parser --chat <chat_file> --start_date <date>
```

The argument values are as follows:

- `<chat>` is the exported WhatsApp chat file as a `.txt`
- `<date>` is the target start date, after which statistics will be collected. It should be passed in quotation marks. Note that at this time, the date must be formatted as `mm/dd/yy` (omitting any leading zeroes). The date must also exist at least once in the WhatsApp export file. If the statistics are returned all zeroes, ensure the date is formatted exactly as it appears in the chat file

### Generating A Graph

The script can also generate a bar graph which displays the number of messages per sender, in descending order. To generate a graph, add the `-g` flag:

```
./parser --chat <chat_file> --start_date <date> -g
```

Optional arguments for the graphing script:

- `--graph_bars <int>`: specify how many bars to graph (e.g. how many senders to display). The default value is 10
- `--graph_title <string>`: add a title to the graph. By default, no title will be added to the graph
- `--graph_file <string>`: specify the file to output the graph to. If no file name is specified, the output will be `graph.jpg`
- `--graph_color <string>`: specify the color for the bars in the graph. This string should be a valid [matplotlib color](https://matplotlib.org/stable/gallery/color/named_colors.html).

### Adding Contacts JSON

Optionally, you can add a JSON file which specifies replacement names for contacts in the output and the graph. The contact being replaced (e.g. a phone number included the WhatsApp export) should be formatted exactly as it appears in the export file. An example of the JSON is as follows:

```
{
    "Contact in WhatsApp Export": "Replacement Name",
    ...
}
```

The JSON file is passed to the parser script with the following argument: `--contacts <contacts.json>`.
