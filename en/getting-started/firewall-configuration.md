metaLinks:
  alternates:
    - &gt;-
      https://app.gitbook.com/s/pt4moEMpSf4BGvjJCzQm/getting-started/firewall-configuration
---

# Firewall Exception Settings

NEXT Market and the Game require bidirectional API communication. NEXT Market requires firewall policy exemption settings for both Inbound and Outbound traffic. Please provide the information listed in the table below to NEXT Market. After the Store is opened, they will proceed with the firewall exemption and then provide the API integration Key information to the game company.

| Environment | Direction                     | Source                                                                                                                                                                         | Destination                                                           |
| ----------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- |
| Preview     | <p>NEXT Market-<br>&gt; Game</p> | <p>147.92.141.97<br>147.92.141.98<br>147.92.141.99<br>147.92.141.100<br>147.92.234.208<br>147.92.234.209<br>147.92.234.220<br>147.92.173.222</p>                               | <mark style="color:blue;">**Game Server Domain or IP and Port Information**</mark>         |
|             | <p>Game-<br>&gt; NEXT Market</p> | <mark style="color:blue;">**IP Address List**</mark>                                                                                                                             | [https://app-sdk.nextmarket.games​](https://app-sdk.nextmarket.games) |
| Production  | <p>NEXT Market-<br>&gt; Game</p> | <p>147.92.139.225<br>147.92.139.226<br>147.92.139.227<br>147.92.139.228<br>147.92.235.249<br>147.92.235.30<br>147.92.238.90<br>147.92.238.95<br>43.223.9.34<br>43.223.9.42</p> | <mark style="color:blue;">**Game Server Domain or IP and Port Information**</mark>         |
|             | <p>Game-<br>&gt; NEXT Market</p> | <mark style="color:blue;">**IP Address List**</mark>
                                                                                                                               | [https://sdk.nextmarket.games​](https://sdk.nextmarket.games)         |

* <mark style="color:blue;">**Information Required from Game Side to NEXT Market (Provided per Preview/Production Environment)**</mark>
  * Server domain or IP and port information for NEXT Market to call the game side (Destination)
  * Source IP used when the game calls NEXT Market (Source)
* Information requiring configuration on the game side (if network settings are needed)
  * Source IP used when NEXT Market calls the game (Source)
  * API Endpoint of NEXT Market to be called by the game (Destination)
