## Установка
```
ansible-playbook -i inventory/hosts install_node-exporter.yml
ansible-playbook -i inventory/hosts install_pgexporter.yml
```


## Проблема на маках
```
Failed to find handler for "/Users/*/.ansible/tmp/ansible-tmp-*/source". Make sure the required command to extract the file is installed.
Command "/usr/bin/tar" detected as tar type bsd. GNU tar required.
Command "/usr/bin/unzip" could not handle archive:   End-of-central-directory signature not found.  Either this file is not
  a zipfile, or it constitutes one disk of a multi-part archive.  In the
  latter case the central directory and zipfile comment will be found on
  the last disk(s) of this archive.
note:  /Users/*/.ansible/tmp/ansible-tmp-1682418229.330871-18676-23750657692873/source may be a plain executable, not an archive
unzip:  cannot find zipfile directory in one of /Users/*/.ansible/tmp/ansible-tmp-*/source or
        /Users/*/.ansible/tmp/ansible-tmp-*/source.zip, and cannot find /Users/*/.ansible/tmp/ansible-tmp-*/source.ZIP, period.
```

Решение
```
export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES
export PATH="/usr/local/opt/gnu-tar/libexec/gnubin:$PATH"
brew install gnu-tar
source ~/.zshrc
```
