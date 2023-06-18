# Massa-Guide
Here is a ENG guide for installing Msaas node in a testnet and gerring reward points. Also there is a [Türkçe Rehber](https://github.com/thisislexar/Massa-Testnet/blob/main/MassaTR.md)
## 1) Let's start installing Node.

``` 
wget -O massaTR.sh https://raw.githubusercontent.com/thisislexar/Massa-Testnet/main/massaTR.sh && chmod +x massaTR.sh && ./massaTR.sh
```
## Here we type `1` and press enter.

![image](https://user-images.githubusercontent.com/101462877/205732305-989494a7-b7f6-4a2d-bd8f-d51a453f8ef3.png) 

## Here we enter a password and make a note of it.

![image](https://user-images.githubusercontent.com/101462877/205732791-d95cabf2-79b7-4079-a503-7a481af0b2c5.png)


## 2) Continue.

## Let's open the screen for Node.
```
source $HOME/.bash_profile
```
```
sudo ufw allow 31244
sudo ufw allow 31245
sudo ufw enable
```
```
cd $HOME/massa/massa-node
screen -S node
```

## Paste the command below as it is, this may take a bit longer.

```
RUST_BACKTRACE=full cargo run --release -- -p $PASSWORD|& tee logs.txt
```

![image](https://user-images.githubusercontent.com/101462877/205748532-3cb07a7a-ef9e-424b-842a-b868a5255f30.png)

## After the logs are as follows, we continue.

![image](https://user-images.githubusercontent.com/101462877/205751293-d8988575-b8b1-4cdc-9803-19115303dd8f.png)


## Let's exit the node screen by doing CTRL + A + D.

![image](https://user-images.githubusercontent.com/101462877/205751487-84c8b024-fad2-4b91-944a-18888ba61816.png)

## Let's go to the client folder and open the Client screen.

```
cd $HOME/massa/massa-client/
screen -S client
```
## Let's run the following command by changing the `<Password>` part.
```
cargo run --release -- -p <Password>
```

## We are waiting for it to end.

![image](https://user-images.githubusercontent.com/101462877/205752092-8717fe0f-349b-40ed-9e95-c11267f06c62.png)

## After it is finished, you will see a screen like this. Enter the following command to create a wallet.

![image](https://user-images.githubusercontent.com/101462877/205752491-b4e5ba75-7cc2-4664-904b-9aa425a030d2.png)

```
wallet_generate_secret_key
```

![image](https://user-images.githubusercontent.com/101462877/205753382-48062e24-5c54-4426-98f8-9c0eb9231a01.png)

## Then you can learn your wallet information with the following command.
```
wallet_info
```

![image](https://user-images.githubusercontent.com/101462877/205755988-0b2d0c20-de5f-42e2-a940-9b5f497585c3.png)
## Next, we change the <your_secret_key> part in the command below and enter it. What you need to write in that section is the script key you see in the wallet_info section.

```
node_add_staking_secret_keys <your_secret_key>
```

For example:

```
node_add_staking_secret_keys S12xxxx6Esnbxxxxxxxxxxxxxxx
```

## Then we go to [Discord](https://discord.gg/massa) and get faucet.

![image](https://user-images.githubusercontent.com/101462877/205754649-60fe17b6-7fef-4797-a669-e0c56a501980.png)

## We return to the terminal again and check whether the token has arrived with the `wallet_info` command.

![image](https://user-images.githubusercontent.com/101462877/205754782-0eef5dbd-8134-42e6-a64c-fe2258c79950.png)

## If our tokens have arrived, we enter the following command by changing the `<ADDRESS>` part.
  
```
buy_rolls <ADRES> 1 0
```  
  
For example like this:
  
```
buy_rolls A12nr9K1XfXBfKw75cQVNZafFRjwMj6pYwpS7tf2RnHaLitv6cG4 1 0
```  

## Afterwards, we go to the testnets-rewards-registration channel in Discord and send a random message.

![image](https://user-images.githubusercontent.com/101462877/205756838-77ed5848-6f31-445d-956b-554893ae70d8.png)

## MassaBot sends us a DM message, we paste the required part of the message into the terminal. Remember to replace your_staking_address with your own wallet address.


<img width="822" alt="Ekran Resmi 2022-12-06 01 33 16" src="https://user-images.githubusercontent.com/101462877/205757206-b565dbc2-0e7a-4a02-8d0b-bbfcc92d9b52.png">

## After the command we entered in the terminal, it gives us an output, and you send this output to the chat with MassaBot.

<img width="1183" alt="Ekran Resmi 2022-12-06 01 35 16" src="https://user-images.githubusercontent.com/101462877/205758713-300ee5a5-f2af-4408-b1f3-6cdada02c503.png">


## Then send MassaBot the server IP where you set up the Massa node.

<img width="823" alt="Ekran Resmi 2022-12-06 01 39 50" src="https://user-images.githubusercontent.com/101462877/205758361-60c4f725-477e-4f7c-817a-3f72cc30a810.png">


## If everything is ok, you will get a message like below.

<img width="839" alt="Ekran Resmi 2022-12-06 01 37 48" src="https://user-images.githubusercontent.com/101462877/205758012-a81bc04a-e94f-46b8-a298-4e93e9da73cf.png">
