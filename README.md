JSON-IPC
===============

thread safe inter process communication via read/write to disc

    JSON IPC

    Concurrent Interprocess Communication via Read and Write JSON

    features to mitigate race condition:

        open file using with statement
        explicit close() in with statement
        finally close()
        json formatting required
        postscript clipping prevents misread due to overwrite without erase
        read and write to the text pipe with a single definition
        growing delay between attempts prevents cpu leak

    to view your live streaming database, navigate to the pipe folder in the terminal:

        tail -F your_json_ipc_database.txt

    :dependencies: os, traceback, json.loads, json.dumps
    :warn: incessant read/write concurrency may damage older spinning platter drives
    :warn: keeping a 3rd party file browser pointed to the pipe folder may consume RAM
    :param str(doc): name of file to read or write
    :param str(text): json dumped list or dict to write; if empty string: then read
    :return: python list or dictionary if reading, else None

    wtfpl2020 litepresence.com
