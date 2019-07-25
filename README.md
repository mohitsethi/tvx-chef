# tvx-chef


- Install chefdk using dpkg `sudo dpkg -i chefdk_4.2.0-1_amd64.deb`
- Verify setup `chef --version`
- TO Upload chef-starter kit to worksstation: `scp -r -v -i <location-of-pem> <directory or file to upload> ubuntu@<ip>:`

- `chef generate cookbook ms`
- Make change to metadata.rb under cookbook directory
- Update recipes/default.rb
- Upload to chef server: `knife cookbook upload ms`
- Bootstraping node `knife bootstrap <fqdn> --ssh-user ubuntu --sudo --node-name ms-tvx-01 -r "recipe[ms::default], recipe[ms1::default]" -y`
