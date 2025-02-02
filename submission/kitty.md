# pallet-kitties
- Calls
  - `create`
  - `transfer`
    - `to: AccountId`
    - `kitty_id: KittyIndex`
     `set_price`
    - `kitty_id: KittyIndex`
    - `new_price: Option<Balance>`
  - `buy`
    - `owner: AccountId`
    - `kitty_id: KittyIndex`
    - `max_price: Balance`

- Storages
  - `Kitties: double_map AccountId, u32 => Option<Kitty>`
  - `NextKittyId: u32`
    - `KittyPrices: map KittyIndex => Option<Balance>`
- Types
  - `struct Kitty([u8; 16])`
- Events
  - `KittyCreated`
    - `owner: AccountId`
    - `kitty_id: u32`
    - `kitty: Kitty`
  - `KittyTransferred`
    - `from: AccountId`
    - `to: AccountId`
    - `kitty_id: KittyIndex`
    `KittyPriceUpdated`
    - `owner: AccountId`
    - `kitty_id: KittyIndex`
    - `price: Option<Balance>`
  - `KittySold`
    - `old_owner: AccountId`
    - `new_owner: AccountId`
    - `kitty_id: KittyIndex`
    - `price: Balance`
