playlist2csv
============

This script parses an `xml` (`.mpl`) file created JRiver MediaCenter to produce a `CSV` file listing the `Artist` and `Name` of each track only. This is useful if your want to import the salient details of a compilation into a labelling (report creation) program.

Usage
-----

    playlist2csv <path_to_input_file> <path_to_output_file>

Dependencies
------------

    - Hpricot
    - FasterCSV
  
Example
-------

Given an .mpl playlist looking like:

      <?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
      <MPL Version="2.0" Title="2010_weird">
        <Item>
          <Field Name="Filename">Z:\music\Electronica\Assorted\The Radioactive Tribute to Kraftwerk\08_Hikashu_Radio Activity.mp3</Field>
          <Field Name="Artist">Hikashu</Field>
          <Field Name="Album">The Radioactive Tribute to Kraftwerk</Field>
          <Field Name="Name">Radio Activity</Field>
          <Field Name="File Type">mp3</Field>
          <Field Name="Genre">Electronica</Field>
          <Field Name="Date">37257</Field>
          <Field Name="Bitrate">192</Field>
          <Field Name="Image File">http://192.168.1.40:10/GetArt?Key=34847</Field>
          <Field Name="Media Type">Audio</Field>
          <Field Name="Last Played">1282979476</Field>
          <Field Name="File Size">10360832</Field>
          <Field Name="Duration">431</Field>
          <Field Name="Number Plays">21</Field>
          <Field Name="Track #">8</Field>
          <Field Name="Date Created">1140420453</Field>
          <Field Name="Date Modified">1140594160</Field>
          <Field Name="Date Imported">1140427848</Field>
          <Field Name="Replay Gain">-12.3097200393676758</Field>
          <Field Name="Peak Level">1</Field>
          <Field Name="Intensity">4</Field>
          <Field Name="BPM">117</Field>
          <Field Name="Album Artist">(Multiple Artists)</Field>
          <Field Name="Bookmark">274671</Field>
          <Field Name="Album Gain">-10.5176105499267578</Field>
          <Field Name="Complete Album">1</Field>
          <Field Name="Mix Album">1</Field>
          <Field Name="Sample Rate">44100</Field>
          <Field Name="Channels">2</Field>
          <Field Name="Bit Depth">16</Field>
          <Field Name="Compression">CBR (MPEG-1 Layer 3)</Field>
          <Field Name="Ambient?">Yes</Field>
          <Field Name="Skip Count">3</Field>
          <Field Name="Last Skipped">1247411370</Field>
          <Field Name="Get Cover Art Info">&lt;XMLPH version="1.0"&gt;&lt;Item Name="LastFailedDate"&gt;40189.91726&lt;/Item&gt;
          &lt;/XMLPH&gt;</Field>
          <Field Name="Library Server Info">m01p://192.168.1.40:10/</Field>
        </Item>
        <Item>
          <Field Name="Filename">Z:\music\Reggae\Suns of Arqa\Solar Activity 1979-2001\00_Suns of Arqa_The Sky Shall Vanish.mp3</Field>
          <Field Name="Artist">Suns of Arqa</Field>
          <Field Name="Album">Solar Activity 1979-2001</Field>
          <Field Name="Name">The Sky Shall Vanish</Field>
          <Field Name="File Type">mp3</Field>
          <Field Name="Genre">Reggae</Field>
          <Field Name="Date">36892</Field>
          <Field Name="Comment">groov[E]mission</Field>
          <Field Name="Bitrate">192</Field>
          <Field Name="Media Type">Audio</Field>
          <Field Name="Last Played">1278177330</Field>
          <Field Name="File Size">8290304</Field>
          <Field Name="Duration">345</Field>
          <Field Name="Number Plays">16</Field>
          <Field Name="Date Created">1130141420</Field>
          <Field Name="Date Modified">1130202796</Field>
          <Field Name="Date Imported">1130144876</Field>
          <Field Name="Replay Gain">-12.4262895584106446</Field>
          <Field Name="Peak Level">1</Field>
          <Field Name="Intensity">2</Field>
          <Field Name="BPM">98</Field>
          <Field Name="Bookmark">154105</Field>
          <Field Name="Album Gain">-11.855722427368164</Field>
          <Field Name="Sample Rate">44100</Field>
          <Field Name="Channels">2</Field>
          <Field Name="Bit Depth">16</Field>
          <Field Name="Compression">CBR (MPEG-1 Layer 3)</Field>
          <Field Name="Ambient?">Yes</Field>
          <Field Name="Dub?">Yes</Field>
          <Field Name="Skip Count">3</Field>
          <Field Name="Last Skipped">1282979134</Field>
          <Field Name="Get Cover Art Info">&lt;XMLPH version="1.0"&gt;&lt;Item Name="LastFailedDate"&gt;40191.84757&lt;/Item&gt;
          &lt;/XMLPH&gt;</Field>
          <Field Name="Library Server Info">m01p://192.168.1.40:10/</Field>
        </Item>
      </MPL>
      
the `playlist2csv` script will output:

    Artist,Name
    Hikashu,Radio Activity
    Suns of Arqa,The Sky Shall Vanish
    
