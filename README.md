A simple Python script that takes an mbox file and converts it into a CSV file.

It was created to process Apache mailing list archives into CSV files that could be used as a corpus for other tools. As such, it does some filtering on the mail:

All mail not sent by the specified author is ignored.
All mail that is to the specified author is ignored.
All mail that is not text/plain is ignored (most messages include text/plain, however).
If a message cannot be converted to ASCII, it is ignored.
An attempt to remove quoted replies, embedded links, and other probably-not-typed-by-the-author text is made.
Additionally, flowed e-mails are processed per RFC 3637.

Usage: python mboxToCsv.py example.mbox "<example@example.com>" > corpus.csv

Limitations: Because of its purpose is to create a corpus for analysis, it errs on the side of removing information. It very likely removes some amount of text that was sent by the author erroneously. It also does not do a perfect job of removing text not sent by the author, so the output should be inspected and the script modified accordingly.