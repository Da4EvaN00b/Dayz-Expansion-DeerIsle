# Expansion Market Documentation

## Market General Settings

Unlike most other settings that may not be map-specific, you can find the `MarketSettings.json` in your `mpmission\dayzOffline.<mapname>\expansion\settings` folder.

### Parameters

**`m_Version`** — Integer

Contains the current setting version number. Never change this value unless you really know what you are doing, as it's used internally for automatic conversion of old settings.

---

**`MarketSystemEnabled`** — Boolean

- `0` = Disables the Market system
- `1` = Enables the Market system

---

**`MaxVehicleDistanceToTrader`**

Maximum distance of a normal size vehicle (car/heli/boat) you own or have driven for it to show in a vehicle trader as sellable, and max distance of vehicle spawn zone.

---

**`MaxLargeVehicleDistanceToTrader`**

Maximum distance of a large size vehicle (e.g. aircraft carrier) you own or have driven for it to show in a vehicle trader as sellable, and max distance of vehicle spawn zone.

---

**`LargeVehicles`** — Array

Array of vehicle class names that should use `MaxLargeVehicleDistanceToTrader` instead of `MaxVehicleDistanceToTrader`.

---

**`LandSpawnPositions`**

Array of spawn positions and orientations for land vehicle spawn zones (e.g. cars). Needs to have at least one entry in a radius of no more than `MaxVehicleDistanceToTrader` or `MaxLargeVehicleDistanceToTrader` from a vehicle trader.

```json
"Position": [11903.400390625, 140.0, 12455.099609375],
"Orientation": [24.0, 0.0, 0.0]
```

---

**`AirSpawnPositions`**

Array of spawn positions and orientations for air vehicle spawn zones (e.g. helis). Needs to have at least one entry within `MaxVehicleDistanceToTrader` or `MaxLargeVehicleDistanceToTrader` from a vehicle trader.

```json
"Position": [11903.400390625, 140.0, 12455.099609375],
"Orientation": [24.0, 0.0, 0.0]
```

---

**`WaterSpawnPositions`**

Array of spawn positions and orientations for water vehicle spawn zones (e.g. boats). Needs to have at least one entry within `MaxVehicleDistanceToTrader` or `MaxLargeVehicleDistanceToTrader` from a vehicle trader.

```json
"Position": [11903.400390625, 140.0, 12455.099609375],
"Orientation": [24.0, 0.0, 0.0]
```

---

**`NetworkCategories`**

Used only internally. Do not touch this setting — it's automatically generated and will be overwritten if changed.

---

**`MarketMenuColors`**

Colors to be used for the market menu. Format is hexadecimal `RRGGBBAA`, hexadecimal `RGBA`, or decimal `R G B A` with range 0–255 (alpha is optional).

You can use [Adobe Color Wheel](https://color.adobe.com/de/create/color-wheel) to generate hex values (add alpha manually after the first six digits if needed).

| Key | Description |
|-----|-------------|
| `BaseColorVignette` | Vignette background color of the menu |
| `BaseColorHeaders` | Color for all header elements |
| `BaseColorLabels` | Color for all label backgrounds |
| `BaseColorText` | Color for all text elements |
| `BaseColorInfoSectionBackground` | Background color for the item info section |
| `BaseColorTooltipsCorners` | Color of tooltip element corners |
| `BaseColorTooltipsSeperatorLine` | Color of the tooltip separator line |
| `BaseColorTooltipsBackground` | Color of the tooltip element background |
| `ColorDecreaseQuantityButton` | Decrease quantity button color |
| `ColorSetQuantityButton` | Set quantity button color |
| `ColorIncreaseQuantityButton` | Increase quantity button color |
| `ColorSellPanel` | Sell panel background color |
| `ColorSellButton` | Sell button color |
| `ColorBuyPanel` | Buy panel background color |
| `ColorBuyButton` | Buy button color |
| `ColorMarketIcon` | Main market trader icon color (upper left corner) |
| `ColorFilterOptionsButton` | Hover color for weapon filter button |
| `ColorFilterOptionsIcon` | Icon color of the weapon filter button |
| `ColorSearchFilterButton` | Search filter button color on hover |
| `ColorCategoryButton` | Category button color on hover |
| `ColorCategoryCollapseIcon` | Category arrow icon color when collapsed |
| `ColorItemButton` | Item entry button color on hover |
| `ColorItemInfoIcon` | Icon color for special condition info icon |
| `ColorItemInfoHasContainerItems` | Info text color when item has container items |
| `ColorItemInfoHasAttachments` | Info text color when item has attachments |
| `ColorItemInfoHasBullets` | Info text color when magazine has bullets |
| `ColorItemInfoIsAttachment` | Info text color when item is attached to another item |
| `ColorItemInfoIsEquipped` | Info text color when item is on inventory slot |
| `ColorItemInfoAttachments` | Info text color in detailed view when item has default attachments |
| `ColorToggleCategoriesText` | Toggle categories button text color |
| `ColorCategoryCorners` | Category element corners color |
| `ColorCategoryBackground` | Category element background color |

---

**`CurrencyIcon`** — String

Path to the icon used as the currency icon within the market menu.

Default: `"DayZExpansion/Market/GUI/icons/coinstack2_64x64.edds"`

---

**`ATMSystemEnabled`** — Boolean

- `0` = Disables ATM lockers
- `1` = Enables ATM lockers

---

**`MaxDepositMoney`** — Integer

Max amount of money players can deposit in the ATM Locker.

---

**`DefaultDepositMoney`** — Integer

Default money added to a player's ATM account when they join the server for the first time.

---

**`ATMPlayerTransferEnabled`** — Boolean

- `0` = Disables ATM player-to-player money transfer
- `1` = Enables ATM player-to-player money transfer

---

**`ATMPartyLockerEnabled`** — Boolean

- `0` = Disables ATM party money account/deposit
- `1` = Enables ATM party money account/deposit

---

**`MaxPartyDepositMoney`** — Integer

Max amount of money players can deposit in the ATM party account.

---

**`SellPricePercent`** — Float

Controls the global sell price difference of all market items. Default is 75% of the buy price. Can be overridden per zone or per item.

---

**`Currencies`** — Array

A list of currencies that can be stored in the player bank account from an ATM.

```json
"Currencies": [
    "expansiongoldbar",
    "expansiongoldnugget",
    "expansionsilverbar",
    "expansionsilvernugget"
]
```

---

## Market Category Settings

**`m_Version`** — Integer

Current setting version number. Do not change.

---

**`DisplayName`** — String

Display name of the market category shown in the market menu. Supports localized strings or raw text.

```json
"DisplayName": "#STR_EXPANSION_MARKET_CATEGORY_AMMOBOXES"
"DisplayName": "Ammo Boxes"
```

---

**`Icon`** — String

Icon of the category. See the [list of default icon names](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-List-of-default-icon-names).

```json
"Icon": "Deliver"
```

---

**`Color`** — String

Hex color code for this category (without `#`). See [color-hex.com](https://www.color-hex.com/).

```json
"Color": "FBFCFEFF"
```

---

**`IsExchange`** — Boolean

If `1`, marks all items in this file as currency items. Ensure this file contains only currency items.

```json
"IsExchange": 0
```

---

**`InitStockPercent`** — Float

Percentage of max stock that each item is initialized to in each zone on first server start.

```json
"InitStockPercent": 75.0
```

---

**`Items`** — Array

Contains all items and associated pricing/stock information.

| Field | Type | Description |
|-------|------|-------------|
| `ClassName` | String | Class name of the item |
| `MaxPriceThreshold` | Integer | Maximum price (when stock is at minimum) |
| `MinPriceThreshold` | Integer | Minimum price (when stock is at maximum) |
| `SellPricePercent` | Float | Sell price percentage; `-1` uses zone setting |
| `MaxStockThreshold` | Integer | Maximum stock overall |
| `MinStockThreshold` | Integer | Minimum stock overall |
| `QuantityPercent` | Integer | Quantity percentage (0–100); `-1` defaults to 100% |
| `SpawnAttachments` | Array[String] | Items attached by default when bought with attachments |
| `Variants` | Array[String] | Color/variant versions shown as dropdown options |

> **Tip:** Set both `MinStockThreshold` and `MaxStockThreshold` to `1` for infinite/static stock.
> Set both `MinPriceThreshold` and `MaxPriceThreshold` to the same value for a static price.

**Examples:**

```json
{
    "ClassName": "ammobox_00buck_10rnd",
    "MaxPriceThreshold": 80,
    "MinPriceThreshold": 40,
    "SellPricePercent": -1.0,
    "MaxStockThreshold": 250,
    "MinStockThreshold": 1,
    "QuantityPercent": -1,
    "SpawnAttachments": [],
    "Variants": []
},
{
    "ClassName": "childbag_red",
    "MaxPriceThreshold": 40,
    "MinPriceThreshold": 20,
    "SellPricePercent": -1.0,
    "MaxStockThreshold": 100,
    "MinStockThreshold": 1,
    "QuantityPercent": -1,
    "SpawnAttachments": [],
    "Variants": ["childbag_blue", "childbag_green"]
},
{
    "ClassName": "fal",
    "MaxPriceThreshold": 2000,
    "MinPriceThreshold": 1700,
    "SellPricePercent": -1.0,
    "MaxStockThreshold": 100,
    "MinStockThreshold": 1,
    "QuantityPercent": -1,
    "SpawnAttachments": ["fal_oebttstck", "mag_fal_20rnd"],
    "Variants": []
}
```

---

## Trader Settings

> **Note:** Traders will only act as traders if they are within the radius of a trader zone. See [TraderZones Settings](#traderzones-settings).

**`m_Version`** — Integer

Current setting version number. Do not change.

---

**`DisplayName`** — String

Display name of the trader shown at the top of the market menu.

```json
"DisplayName": "#STR_EXPANSION_MARKET_TRADER_VEHICLE_PARTS"
"DisplayName": "Vehicle Parts"
```

---

**`MinRequiredReputation`** — Integer *(Expansion Hardline only)*

Minimum reputation required from the player to interact with this trader.

```json
"MinRequiredReputation": 0
```

---

**`MaxRequiredReputation`** — Integer *(Expansion Hardline only)*

Maximum reputation required from the player to interact with this trader.

```json
"MaxRequiredReputation": 2147483647
```

---

**`TraderIcon`** — String

Icon displayed at the top of the market menu. See [List of default icon names](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-List-of-default-icon-names).

```json
"TraderIcon": "Gas"
```

---

**`Currencies`** — Array[String]

Class names of currencies this trader will accept. Must be configured in your Market folder first.

```json
"Currencies": [
    "ExpansionBanknoteHryvnia",
    "expansionbanknoteeuro"
]
```

---

**`Categories`** — Array[String]

Filenames (without `.json` extension) of market categories this trader should show. Supports buy/sell mode suffix using `:<value>`.

| Value | Behavior |
|-------|----------|
| `0` | Can only be bought from this trader |
| `1` | Buy and Sell |
| `2` | Can only be sold to this trader |
| `3` | Not visible but available for item customization/attachments |

```json
"Categories": {
    "Cars:1",
    "Vehicle_Parts:3"
}
```

---

**`Items`** — Map[String, Integer]

A list of specific items the trader can sell/buy, with the same buy/sell integers as Categories.

```json
"Items": {
    "expansioncarkey": 0,
    "engineoil": 2
}
```

---

## Trader and NPC Entity Setup

Trader entities are configured using `.map` files located at:

```
mpmissions/dayzoffline.<MapName>/expansion/traders/MyTrader.map
```

Each trader entity needs one line per entry in this format:

```
<TraderEntityClassName>.<TraderFileName>|<Position>|<Orientation>|<Gear>
```

**Example:**
```
ExpansionTraderDenis.Weapons|11833.576 140.605 12469.492|110 0 0|Jeans_Blue,TSHirt_Blue
```

**With attachments:**
```
ExpansionTraderDenis.Weapons|11833.576 140.605 12469.492|110 0 0|Jeans_Blue,TSHirt_Blue,AKM+Mag_AKM_30Rnd+KobraOptic
```

**With special keywords (name, loadout, faction):**
```
ExpansionTraderDenis.Weapons|11833.576 140.605 12469.492|110 0 0|name:Mark,loadout:MyTraderLoadout
ExpansionTraderAIDenis.Weapons|11833.576 140.605 12469.492|110 0 0|name:Mark,loadout:MyTraderLoadout,faction:Guards
```

### Field Descriptions

- **TraderEntityClassName** — The entity/NPC class name (e.g. `ExpansionTraderDenis`)
- **TraderFileName** — The trader config file base name (without `.json`) from `ExpansionMod\Traders`
- **Position** — Single vector or comma-delimited list of vectors (waypoints for AI traders only)
- **Orientation** — Single vector indicating the direction the NPC faces
- **Gear** — Comma-delimited list of items in the trader's inventory; use `+` for attachments

### Default Static Trader Entities

```
ExpansionTraderPumpkin
ExpansionTraderZucchini
ExpansionExchangeMachine
ExpansionTraderLockerClosedBlueV1
ExpansionTraderLockerClosedBlueV2
ExpansionTraderLockerClosedBlueV3
ExpansionTraderLockerClosedV1
ExpansionTraderLockerClosedV2
ExpansionTraderLockerClosedV3
```

### Default Static Trader NPCs

```
ExpansionTraderMirek    ExpansionTraderDenis    ExpansionTraderBoris
ExpansionTraderCyril    ExpansionTraderElias    ExpansionTraderFrancis
ExpansionTraderGuo      ExpansionTraderHassan   ExpansionTraderIndar
ExpansionTraderJose     ExpansionTraderKaito    ExpansionTraderLewis
ExpansionTraderManua    ExpansionTraderNiki     ExpansionTraderOliver
ExpansionTraderPeter    ExpansionTraderQuinn    ExpansionTraderRolf
ExpansionTraderSeth     ExpansionTraderTaiki    ExpansionTraderLinda
ExpansionTraderMaria    ExpansionTraderFrida    ExpansionTraderGabi
ExpansionTraderHelga    ExpansionTraderIrena    ExpansionTraderJudy
ExpansionTraderKeiko    ExpansionTraderEva      ExpansionTraderNaomi
ExpansionTraderBaty
```

### Default AI Trader NPCs

```
ExpansionTraderAIMirek    ExpansionTraderAIDenis    ExpansionTraderAIBoris
ExpansionTraderAICyril    ExpansionTraderAIElias    ExpansionTraderAIFrancis
ExpansionTraderAIGuo      ExpansionTraderAIHassan   ExpansionTraderAIIndar
ExpansionTraderAIJose     ExpansionTraderAIKaito    ExpansionTraderAILewis
ExpansionTraderAIManua    ExpansionTraderAINiki     ExpansionTraderAIOliver
ExpansionTraderAIPeter    ExpansionTraderAIQuinn    ExpansionTraderAIRolf
ExpansionTraderAISeth     ExpansionTraderAITaiki    ExpansionTraderAILinda
ExpansionTraderAIMaria    ExpansionTraderAIFrida    ExpansionTraderAIGabi
ExpansionTraderAIHelga    ExpansionTraderAIIrena    ExpansionTraderAIJudy
ExpansionTraderAIKeiko    ExpansionTraderAIEva      ExpansionTraderAINaomi
ExpansionTraderAIBaty
```

> **Note:** AI traders have a higher performance impact than static NPCs.

---

## TraderZones Settings

Unlike most other settings, the traderzones folder is found at:

```
mpmission\dayzOffline.<mapname>\expansion\traderzones\
```

Traders will only act as traders if they are within the radius of a trader zone. **Zones are spheres** — altitude for Position must be set correctly.

**`m_Version`** — Integer

Current setting version number. Do not change.

---

**`m_DisplayName`** — String

Market zone display name. Used for logging only.

---

**`Position`** — Vector

Center position of the market zone in the game world.

---

**`Radius`** — Float

Defines the size (radius) of the trader zone.

---

**`BuyPricePercent`** — Float

Buy price multiplier for all items in this zone. Default is `100%` (full price as calculated from stock/thresholds).

---

**`SellPricePercent`** — Float

Sell price multiplier for all items in this zone. Default `-1.0` uses the global value from market settings.

---

**`Stock`** — Map\<String, Integer\>

Contains all items purchasable in this zone and their current stock. Stock of `0` means the trader will only sell the item after a player has sold at least one to the trader first.
