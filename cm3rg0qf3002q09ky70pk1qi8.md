---
title: "Mấy thứ phải làm trên WSL mỗi khi cài lại"
datePublished: Thu Nov 21 2024 15:04:11 GMT+0000 (Coordinated Universal Time)
cuid: cm3rg0qf3002q09ky70pk1qi8
slug: may-thu-phai-lam-tren-wsl-moi-khi-cai-lai
tags: github, wsl

---

Ubuntu 24 mấy bữa rồi mà thấy WSL đang Ubuntu 22 cũng hơi nhột. Để cả 2 cái thì thấy nặng nên quyết tâm backup lại code rồi xóa U22 lên U24 coi sao và thấy là bản cài mới chưa sẵn sàng để làm việc mà mấy cái setup lại quên hết rồi nên thôi lần này quyết tâm ghi lại

## git và github

Default có sẵn git rồi còn chưa thì cứ mạnh tay

`sudo apt install git`

Tiếp theo là cài github client bằng lệnh

`sudo apt install gh`

Sau đó login vào github và xem cái email của mình rồi chạy lệnh config git thôi. Nhớ dùng tên và email của mình

`git config --global` [`user.name`](http://user.name) `"abc"`

`git config --global` [`user.email`](http://user.email) `"abc@def.ghi"`

Tiếp theo ở trong github [https://github.com/settings/tokens](https://github.com/settings/tokens) generate một cái token. Thời điểm 21/11/2024 nhớ chọn classic chứ cái mới chưa chạy được. Ở phần scope thì chọn các mục sau: 'repo', 'read:org', 'workflow'. Xong thì nhớ copy cái token này

```plaintext
gh auth login 
? Where do you use GitHub? GitHub.com 
? What is your preferred protocol for Git operations on this host? HTTPS 
? How would you like to authenticate GitHub CLI? Paste an authentication token 
Tip: you can generate a Personal Access Token here https://github.com/settings/tokens 
The minimum required scopes are 'repo', 'read:org', 'workflow'. 
? Paste your authentication token: ****************************************
- gh config set -h github.com git_protocol https 
✓ Configured git protocol 
! Authentication credentials saved in plain text 
✓ Logged in as abc 
! You were already logged in to this account
```

Vậy là xong xài được github rồi đó, có thể chạy lệnh push hay clone các private repo. Hoặc xài extension github trong vscode ngon lành