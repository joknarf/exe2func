# exe2func
unix executable to shell function

Convert any executable to shell function
So you can get all your scripts/exe in 1 file, to copy anywhere.
Ready to be used anywhere

### Concept:
the exe file (script or binary) is compressed/base64 in the function
when calling the function decode/decomress in /tmp

Really handy when you need to manage thousands of servers
to have same env/toolbox when connecting to any of them

### Example:
Putting the exe2func script itself in a function:

```
$ ./exe2func ./exe2func exe2func
function exe2func
{
    cat - <<'EOF'| base64 -d| bzip2 -dc >/tmp/.exe2func
QlpoOTFBWSZTWcc1170AAGbfgEAQf/+1F8sBmg4/59/+QAIJ2nIyhKTSaDRDBR5TRspo0AZqDJoN
NPUGqnjQSepiaaaANAPUAAANqAanpJigaPUyAGgaAAAAAEppNTTSmMiaGm1A0AGgGgABRIMfP+0r
c5fjbN7Wruv+V7JLc1Ks2XjYX+sdYgRibCw3pMaU3mOITAuiRmDiiY+2sIcEhFakNaagJBo4fn4I
oOGPvHSZjhIJw1pAr6noDFQUymnJMKjwLj9rlbQSjs3KkqHz1WWY9BO3VZlFUxq4gZJPevhnc5gT
xv13hUG3x1jWaMkVc0LWFzAX3DBt3cHPzd8dssaasOLUpSU9JDcya1GnNQS7IbSjFBLAepI0alZ7
B8nuE24CY/FxviRkLr87RkUQxCOmrwjzlWE/tiTRHCvZ3S+zsco0pCB7sEbHgLKgGkiiAkCgRo2I
sha2QshLKY4G6XkypFVIOLe2uiNIm1nCJUDQ1Hs9AgICFOFJBMjUsTDz25FpF1pbJ9qmwjRlITHM
8Br5h7RIU+UnSB1pyGcJWo3mdfrGBn8hqm3B7oG/jKE85Ua9P5JsyIvuBx7LIAvwsPrFdW3JrClh
KuJJ7gkiW9BzEFcVSNHQQLExoTEwmN8ryJR4cFVYmulsR9L9LAeOFFTKybBk8A6vrygxzkpqfn6q
Ko0qZPqY16QUeWB3cdtYtlhWOTUK2LhszDjKJ4cdDcGFdo5eCJZiqidYEqMYswITw6FXlJLHpOKO
M5moNdGSXjDj/i7kinChIY5rr3o=
EOF
    chmod +x /tmp/.exe2func
    /tmp/.exe2func "$@"
    typeset e=$?
    rm /tmp/.exe2func
    return $e
}
```
