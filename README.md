# tvx-chef


- Install chefdk using dpkg `sudo dpkg -i chefdk_4.2.0-1_amd64.deb`
- Verify setup `chef --version`
- TO Upload chef-starter kit to worksstation: `scp -r -v -i <location-of-pem> <directory or file to upload> ubuntu@<ip>:`

- `chef generate cookbook ms`
- Make change to metadata.rb under cookbook directory
- Update recipes/default.rb
- Upload to chef server: `knife cookbook upload ms`
- Bootstraping node `knife bootstrap <fqdn> --ssh-user ubuntu --sudo -i <path-to-ec2-pem> --node-name ms-tvx-01 -r "recipe[ms::default], recipe[ms1::default]" -y`
- Knife Search: `knife search "platform:ubuntu"` `knife search "chef_environment:teststage"` `knife search "chef_environment:teststage AND platform:ubuntu"`
  - Documentation: https://docs.chef.io/knife_search.html
- Search & Execute command: `knife ssh "platform:ubuntu" "uptime" --ssh-user ubuntu -i surya-key.pem -a ec2.public_hostname`
- Powershell resource: `https://docs.chef.io/resource_powershell_script.html`

- Templates
  - `mkdir -p templates/default`
  - `cp files/default/index.html templates/default/index.html.erb`
  
### GIT


sql_server_install 'sql1_coda' do
    action :install
end


Git Commands

- `git init`
- `git add <file>`
- `git status`
- `git commit <file>` # provide the commit message later
- `git log` # to list commit 
- `git config --global user.name` # Sets the git username at user leve.
- `git commit --amend <file>` # amend last commit
- create file .gitignore
- `git add .gitignore`
- `git commit .gitignore -m '<message>'`
- 
