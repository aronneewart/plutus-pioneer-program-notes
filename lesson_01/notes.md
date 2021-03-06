# Lesson 1
           
Install the *last version* of plutus playground

#### Install Nix

```shell
curl -L https://nixos.org/nix/install | sh
source ~/.nix-profile/etc/profile.d/nix.sh
```
#### Add IOHK binary cache
       
```shell
mkir -p ~/.config/nix
touch ~/.config/nix/nix.conf
```        
Add the following into `~/.config/nix/nix.conf` :

```
substituters        = https://hydra.iohk.io https://iohk.cachix.org https://cache.nixos.org/
trusted-public-keys = hydra.iohk.io:f/Ea+s+dFdN+3Y/G+FDgSq+a5NEWhJGzdjvKNGv0/EQ= iohk.cachix.org-1:DpRUyj7h7V830dp/i6Nti+NEO2/nhblbov/8MW7Rqoo= cache.nixos.org-1:6NCHdD59X431o0gWypbMrAURkbJ16ZPMQFGspcDShjY=
```
> **Note**: Instead you can use `/etc/nix/nix.conf` if you want to make the cache available to all users
     
#### Clone the plutus repository
           
```shell
git clone https://github.com/input-output-hk/plutus
```        

The file `shell.nix` contains the instructions for *nix* to build all the necessary tools used in this repo such as `ghc`, `cabal`, `stake`, `plutus-playground-server`, `npm`, ...
                      
```shell
cd plutus
nix-shell
```

#### Run server
           
```shell
cd plutus
nix-shell
cd plutus-playground-server
plutus-playground-server
```        
#### Run client
           
```shell
cd plutus
nix-shell
cd plutus-playground-client
npm run start
```

#### Enjoy!

Plutus playground should be running in `https://localhost:8009`
