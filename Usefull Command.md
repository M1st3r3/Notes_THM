
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

