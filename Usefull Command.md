
**Info On Tables Sqlite3**:
```mysql
sqlite> PRAGMA table_info(customers);
0|cudtID|INT|1||1
1|custName|TEXT|1||0
2|creditCard|TEXT|0||0
3|password|TEXT|1||0
```

**Read all tables:**
```mysql
sqlite> SELECT * FROM customers;
0|Joy Paulson|4916 9012 2231 7905|5f4dcc3b5aa765d61d8327deb882cf99
1|John Walters|4671 5376 3366 8125|fef08f333cc53594c8097eba1f35726a
2|Lena Abdul|4353 4722 6349 6685|b55ab2470f160c331a99b8d8a1946b19
3|Andrew Miller|4059 8824 0198 5596|bc7b657bd56e4386e3397ca86e378f70
4|Keith Wayman|4972 1604 3381 8885|12e7a36c0710571b3d827992f4cfe679
5|Annett Scholz|5400 1617 6508 1166|e2795fc96af3f4d6288906a90a52a47f
```

**Get All Users in a System**: 
```bash
sed -n '/^\([^:]\+\):[^:]\+:[1-9][0-9]\{3\}/ { s/:.*//; p }' /etc/passwd
```

**Find the OS version**:
```bash
cat /etc/os-release
```


**Verify Intergrety in 3rd library:** [SriHash](https://www.srihash.org/)

**To Put Space in an HTTP Request(comment)** : ```&23```

If a directory of uploaded files is blocked you can still access the file if you know its name (ex: you dropped an reverse shell)

---

Steps for a file exploitation
- See the technology used by the website ( Manually or Burpsuite Header -> (server,x-powered-by) )
- Inspect the source code on the client side of the upload page see if there are any client-side blocking
- Upload a normal file and see how the website react , try to see where the file is uploaded 
- Bypass the client side filtering and see if there are any server side filtering

-> To discover server filtering:
- If you can successfully upload a file with a totally invalid file extension (e.g. `testingimage.invalidfileextension`) then the chances are that the server is using an extension _blacklist_ to filter out executable files. If this upload fails then any extension filter will be operating on a whitelist.

- Try re-uploading your originally accepted innocent file, but this time change the magic number of the file to be something that you would expect to be filtered. If the upload fails then you know that the server is using a magic number based filter.

- As with the previous point, try to upload your innocent file, but intercept the request with Burpsuite and change the MIME type of the upload to something that you would expect to be filtered. If the upload fails then you know that the server is filtering based on MIME types.

- Enumerating file length filters is a case of uploading a small file, then uploading progressively bigger files until you hit the filter. At that point you'll know what the acceptable limit is. If you're very lucky then the error message of original upload may outright tell you what the size limit is. Be aware that a small file length limit may prevent you from uploading the reverse shell we've been using so far.