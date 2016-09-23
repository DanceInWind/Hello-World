参考资料
http://blog.csdn.net/keyboardota/article/details/7603630
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#adding-your-ssh-key-to-the-ssh-agent
https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/


大概步骤
1.Open Git Bash.
2.eval $(ssh-agent -s)
3.ssh-add ~/.ssh/id_rsa
4.Add the SSH key to your GitHub account.
clip < ~/.ssh/id_rsa.pub 
github->setting->SSH and GPG keys.->Add SSH key
.







其他资料
http://suselinks.us/two-ways-to-skip-password-typing-when-using-https-github/