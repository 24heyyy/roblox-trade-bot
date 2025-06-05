# roblox-trade-bot

Currently the most advanced trade bot available.

⚠️ This project was previously paid, but due to a VPS failure that wiped all user data and keys, I decided to release it for free rather than rebuilding everything.

❗ DO NOT sell or claim ownership of this project.

💬 Need help? Join the support server: https://discord.gg/SwCsTNRxUC (My main server with all my projects), https://discord.gg/GuWvD24z (Official trade bot server)


# Setup

1. **Install Python**  
   If you don’t already have Python, download and install it from: https://www.python.org/  
   Make sure to check the option “Add Python to PATH” during installation.

2. **Install Dependencies**  
   Open your command prompt (CMD) and run:

   ```
   pip install aiohttp
   pip install requests
   pip install aiofiles
   ```

3. **Configure the Bot**  
   Open the configuration file and fill in your account details as shown below.

---

# Configuration

Example structure:

```
{
    "accounts": [
        {
            "account": {
                "cookie": "YOUR_ROBLOSECURITY_COOKIE_HERE",
                "opt_secret": "YOUR_2FA_SECRET"
            },
            "rolimon": {
                "roli_verification_token": "YOUR_ROLI_TOKEN",
                "ads": {
                    "sleep_time": 900,
                    "offers": []
                },
                "limiteds_value_updater_sleep_time": 60
            },
            "trade": {
                "sleep_time": 15,
                "items": {
                    "not_for_trade": [],
                    "not_accepting": []
                },
                "algorithm": {
                    "bulk_penalty_rate": 0.03,
                    "upgrade_penalty_multiplier": 1.05,
                    "demand_multiplier": 100,
                    "rare_multiplier": 100,
                    "base_divisor": 1000,
                    "min_receiving_value_when_downgrading": 1,
                    "max_giving_value_when_upgrading": 1,
                    "max_edge": 1.1,
                    "batch_size": 5000,
                    "max_pairs": 500000,
                    "value_only": false,
                    "max_edge_value": 1.2,
                    "max_edge_algorithm": 1.05,
                    "lower_rap_only_item": 0.75,
                    "max_item_ratio_upgrade": 0.65,
                    "min_item_ratio_upgrade": 0.1,
                    "downgrader_min_items": 1,
                    "downgrader_max_items": 3,
                    "upgrader_min_items": 2,
                    "upgrader_max_items": 4
                }
            },
            "webhook": "https://discord.com/api/webhooks/..."
        }
    ]
}
```

---

# Configuration Breakdown


## 🧾 Account Settings
- `"cookie"`: Your Roblox .ROBLOSECURITY cookie. Use a browser extension like "Cookie Editor" to find and copy this.
- `"opt_secret"`: Your 2FA secret, obtained when enabling 2FA on your account.
- `"roli_verification_token"`: Your Rolimon verification cookie (_RoliVerification).

## 📢 Rolimon Ad Settings
- `"sleep_time"`: Seconds to wait between posting ads (default: 900).
- `"offers"`: Leave empty to auto-generate or specify manually.

### Offer Example
```
"offers": [
    {
        "offer_item_ids": [123456789, 987654321],
        "request_item_ids": [112233445, 998877665],
        "request_tags": ["demand", "robux"]
    }
]
```

### Tags:
- `"any"`: Any item
- `"demand"`: In-demand items
- `"rares"`: Rare items
- `"rap"`: High RAP items
- `"upgrade"`: Upgrade trades
- `"robux"`: Robux-related trades

## 🔄 Value Updating
- `"limiteds_value_updater_sleep_time"`: Seconds between Rolimon scans (default: 60).

## ⚖️ Trade Settings
- `"sleep_time"`: Delay between sending trades (default: 15).
- `"not_for_trade"` and `"not_accepting"`: Excluded item IDs.

## 🧠 Algorithm Settings
- `"bulk_penalty_rate"`: Penalty for each extra item in bulk trades.
- `"upgrade_penalty_multiplier"`: Score penalty for upgrades.
- `"demand_multiplier"` / `"rare_multiplier"`: Score boost for demand/rare items.
- `"base_divisor"`: Scales base price for scoring.
- `"min_receiving_value_when_downgrading"`: Min multiplier when downgrading.
- `"max_giving_value_when_upgrading"`: Max allowed giving ratio for upgrades.
- `"max_edge"`: Max score/value difference allowed.
- `"batch_size"`: Number of trades evaluated per batch.
- `"max_pairs"`: Max number of trade pairs generated.
- `"value_only"`: If true, only items with value are considered.

### Advanced Algorithm Tuning
- `"max_edge_value"` / `"max_edge_algorithm"`: Max allowed value or score gap.
- `"lower_rap_only_item"`: Multiplier for RAP-only items.
- `"max_item_ratio_upgrade"` / `"min_item_ratio_upgrade"`: Prevents uneven upgrades.
- `"downgrader_min_items"` / `"downgrader_max_items"`: Item limits for downgrade trades.
- `"upgrader_min_items"` / `"upgrader_max_items"`: Item limits for upgrade trades.



### PLS STAR THIS ⭐
every 30 stars i will do an update including every suggestion
