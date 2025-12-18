---
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Set up API Connections

#### Prerequisites

* Admin or owner access to the store’s admin panel.
* Permission to create API keys, apps, or integrations.
* Basic understanding of which entities you plan to migrate (products, customers, orders, blog posts, etc.).

#### Get API Key / API Access Token

<details>

<summary><strong>3dCart (Shift4Shop)</strong></summary>

1. Log in to your 3dCart / Shift4Shop admin panel.
2. Go to **Modules** → find and open **REST API** or **API**.
3. If API is disabled, enable it.
4. Click **Add / Create Key** (or similar).
5. Give the key a name such as “Next-Cart Migration”.
6. Grant **read** permissions for:
   * Products / Items
   * Customers
   * Orders
   * Categories and other data types you plan to migrate.
7. Save the key and copy the generated **API Key** (and API Username/Store URL if shown).

**Fields to Use in Next-Cart**

* **Store URL**
* **API Key** (and, if applicable, API Username)

</details>

<details>

<summary><strong>AmeriCommerce</strong></summary>

1. Sign in to your AmeriCommerce admin.
2. Go to **Tools → Apps & Addons → API Apps & Integrations**.
3. Create a **new app** and give it a clear name (e.g. “Next-Cart Migration Tool”) and short description.
4. Choose **Single Token Flow** as the authentication method so a single token is generated.
5. In the scopes/permissions section, grant access to **customers, orders, catalog/products and other data** that needs to be migrated (view/change as required by your process).
6. Save the app to generate the **Access Token**. Copy it immediately and store it securely.

**Values to enter in the migration tool**

* **Store URL** – your AmeriCommerce store URL, e.g. `https://xxxxxx.americommerce.com`.
* **Access Token** – the token generated for this private app

</details>

<details>

<summary><strong>BigCommerce</strong></summary>

1. Log in to your BigCommerce store’s control panel.
2. Go to **Settings** → **API Accounts** (or **Advanced Settings → API Accounts**, depending on UI).
3. Click **Create API Account** → choose **Create V2/V3 API Token**.
4. Name the API account (e.g., “Next-Cart Migration”).
5. Set at least **Read** access for:
   * Customers
   * Orders
   * Products
   * Store Information, and any other relevant resources.
6. Save; BigCommerce will show:
   * **Client ID**
   * **Client Secret**
   * **Access Token**
   * API Path (store API URL)
7. Download the credentials file and copy the required values.

**Fields to Use in Next-Cart**

* **API Path** (BigCommerce API URL)
* **Access Token**
* **Client ID** (if required)

</details>

<details>

<summary><strong>Bluepark</strong></summary>

1. Log in to your **Bluepark admin**.
2. From the left menu, open **Users → Admin Manager**.
3. Click your **admin user** to open the details screen.
4. Go to the **Properties** tab and locate **Admin Panel Access and Authorisation**.
5. Enable **API access** if it is disabled.
6. Note the displayed **API Username**, **API Key**, and **API access URL**.

**Values to enter in the migration tool**

* **Store URL** – the **API access URL** from Bluepark.
* **API Username** – as shown in the Admin Panel Access block.
* **API Key** – as shown in the same block.

</details>

<details>

<summary><strong>Clover</strong></summary>

1. Log in to your **Clover dashboard**.
2. Go to **Account & Setup** from the left menu.
3. Under **About Your Business**, select **Merchants** and copy the **Merchant ID** shown for your business.
4. Return to **Account & Setup**, then in **Business Operations** choose **API Tokens**.
5. Click **Create new token**.
6. Enter a token name (e.g. “Migration Tool”) and enable all required **Read** permissions for the data you will migrate.
7. Confirm to create the token and copy the **Private token** shown.

**Values to enter in the migration tool**

* **Merchant ID** – from the Merchants page.
* **API Token** – the Private token you generated.

</details>

<details>

<summary><strong>CommerceHQ</strong></summary>

1. Sign in to your CommerceHQ admin.
2. Go to **Dashboard → Apps Store**.
3. Click **Add a Private App**.
4. Enter a recognizable **Private app name** (e.g. “Migration Tool”).
5. In **Access options**, grant access to the resources that must be migrated (e.g. **Products, Orders, Customers**).
6. Save to create the private app.
7. In **Installed Apps**, open the private app’s **Settings** to view the **API Key** and **API Password**, then copy both.

**Values to enter in the migration tool**

* **Store URL** – your CommerceHQ store URL.
* **API Key** – from the private app.
* **API Password** – from the same screen.

</details>

<details>

<summary>CoreCommerce</summary>

1. Log in to the **CoreCommerce Admin Dashboard**.
2. Go to **Settings → API Settings**.
3. Enable the **API** option.
4. Note the **Username** shown (often pre-filled as “api”); this is your **API Username**. Save the page.
5. Under **Settings**, open **External Access Keys**.
6. Create a **new key**, name it clearly (e.g. “Migration”), and save.
7. After saving, copy the generated **Key** – this is your **API Key**.

**Values to enter in the migration tool**

* **API Username** – from API Settings.
* **API Key** – from External Access Keys.

</details>

<details>

<summary><strong>Ecwid</strong></summary>

1. Log in to your **Ecwid Admin Panel**.
2. Open a new tab and visit the **Ecwid API Playground**: `https://api-playground.ecwid.com/`.
3. Click **Connect with Ecwid** and authorize if prompted.
4. After the page reloads, locate the **Personal Collection URL** (the long URL ending with `.json.postman_collection`).
5. Copy the entire URL.

**Values to enter in the migration tool**

* **Store URL** – your Ecwid store URL.
* **Personal Collection URL** – paste the full URL from the API Playground.

</details>

<details>

<summary><strong>eBay</strong></summary>

1. Open the dedicated authorization link provided by Next-Cart for eBay (as specified in your admin or documentation).
2. You’ll be redirected to the official eBay website. Log in with your eBay account.
3. Follow the prompts to **grant access** to the migration application.
4. Once access is granted, an **API Key** for eBay will be shown.
5. Copy the API Key and keep it in a secure place.

**Values to enter in the migration tool**

* **API Key** – the key provided after authorization.

</details>

<details>

<summary><strong>ePages</strong></summary>

1. Identify your **Source Store URL** by visiting your live store and copying the URL (e.g. `https://your-store.epages.com`).
2. Derive your **API URL** by appending `/api` to the store URL (e.g. `https://your-store.epages.com/api`).
3. Log in to your **ePages admin** and go to **Apps**.
4. Create a **private app**, give it a clear name (e.g. “Migration Tool”), and save.
5. In the app’s **Permissions/Scopes**, assign **read** permissions for all entities you will migrate (products, categories, orders, customers, etc.).
6. Save to generate credentials, then copy the **Access Token** (and Client ID/Secret if shown).

**Values to enter in the migration tool**

* **Source Store URL** – live store URL.
* **API URL** – store URL with `/api`.
* **Access Token** – from the private app.

</details>

<details>

<summary><strong>Etsy</strong></summary>

1. Log in to your **Etsy account**.
2. Open the **Etsy Developer portal**: `https://www.etsy.com/developers/your-apps`.
3. Accept any developer terms if prompted.
4. Create a **new app** and fill in the required fields (app name, short description, site URL).
5. For type and usage, select options appropriate for **seller tools** used by you/your clients.
6. Save to create the app. The app detail page will show **KEYSTRING (API Key)** and **SHARED SECRET**.
7. Copy both values and store them securely.

**Values to enter in the migration tool**

* **API Key** – Etsy **Keystring**.
* **API Secret** – Etsy **Shared Secret**.

</details>

<details>

<summary><strong>Helcim</strong></summary>

1. Log in to the Helcim admin.
2. Go to **All Tools → Settings → My Account** and copy your **Account ID** from Merchant Information.
3. Return to **All Tools** and open **Integrations**.
4. Open **API Access Configurations → Legacy API Access**.
5. Create **New API Access**.
6. Enter a name (e.g. “Migration”), mark it as **Active**, and grant **View** permissions to all required data types. Save.
7. After saving, copy the generated **API Token**.

**Values to enter in the migration tool**

* **Store URL** - your Helcim store URL.
* **Account ID** – from Merchant Information.
* **API Token** – from API Access Information.

</details>

<details>

<summary><strong>Jumpseller</strong></summary>

1. Log in to the **Jumpseller admin panel**.
2. Click the **Accounts** icon (bottom left).
3. Select your **admin account**.
4. In the right sidebar, locate the **API Login** and **Auth Token**.
5. Copy both values.

**Values to enter in the migration tool**

* **Store URL** – admin domain, e.g. `https://xxxxxx.jumpseller.com`.
* **API Login** – from account details.
* **Auth Token** – from the same sidebar.

</details>

<details>

<summary><strong>LemonStand</strong></summary>

1. Log in to the **LemonStand backend**.
2. Go to the **Integrations** menu.
3. Open the **API Keys** section.
4. Add a **new API Key**.
5. After creation, copy the **API Token**.

**Values to enter in the migration tool**

* **Store URL** - your Lemonstand store URL.
* **API Token** – the token from your new API Key.

</details>

<details>

<summary><strong>Lightspeed</strong></summary>

1. Log in to your Lightspeed back office.
2. Navigate to **Settings → API Keys / Integrations**.
3. Create a new API key or enable the existing one.
4. Set required **Read** permissions for products, customers, orders, etc.
5. Copy:
   * API Key
   * API Secret (if provided)
   * Store URL / API Endpoint

**Fields to Use in Next-Cart**

* **Store URL** / **Endpoint**
* **API Key**
* **API Secret** (if applicable)

</details>

<details>

<summary><strong>LogiCommerce</strong></summary>

1. Confirm your **Source Store URL** by visiting your live store and copying the URL.
2. Log in to the **LogiCommerce admin panel**.
3. Open **Apps**, then the **Private apps** tab.
4. Click **Add** to create a new private app.
5. Set an **App name** (e.g. “Migration Tool”) and configure **App Scopes** with read access for products, categories, orders, customers, and any other required entities.
6. Save or generate access data.
7. Copy the **App ID (Client ID)** and **App Key (Client Secret)** from the generated credentials.

**Values to enter in the migration tool**

* **Store URL** – your public store URL.
* **App ID / Client ID**.
* **App Key / Client Secret**.

</details>

<details>

<summary><strong>Maropost (Neto by Maropost)</strong></summary>

1. Log in to your Neto Control Panel (e.g., `yourdomain.com.au/_cpanel`).
2. Go to **Settings & Tools → All Settings & Tools**.
3. Under **Developer Tools**, select **API Settings**.
4. On the API Settings page, click **Regenerate** to create a fresh API key, then **Save Changes**.
5. Copy the **API Key** displayed.

**Fields to Use in Next-Cart**

* **Store URL**
* **API Key**

</details>

<details>

<summary><strong>Miva Merchant</strong></summary>

1. Log in to **Miva Admin**.
2. Go to **Settings → User Management → API Tokens**.
3. Click **Add API Token**.
4. Fill in a **Name** (e.g. “Migration”), leave the system-generated **Endpoint URL** and **Access Token**, and configure Allowed IPs and security options as required by your environment.
5. Save the token.
6. Back in the API Tokens list, open the token’s **Groups** and assign the groups that cover accounting/reporting, customer service, marketing, order fulfillment, and product management so all required data can be accessed.

**Values to enter in the migration tool**

* **Store URL** – your public store URL.
* **Endpoint URL** – from the API Token details.
* **Access Token** – from the same token.

</details>

<details>

<summary><strong>PinnacleCart</strong></summary>

1. Log in to the **PinnacleCart admin panel**.
2. Navigate to **Settings → Advanced settings → API access**.
3. Enable the checkbox to turn on **API Enabled**.
4. Enter a **Username** and **Password** for API access.
5. Click **Generate** to create a **Security Token**.
6. Save the configuration.

**Values to enter in the migration tool**

* **API Username**.
* **API Password**.
* **Security Token**.

</details>

<details>

<summary>Plentymarkets (PlentyONE)</summary>

1. Log in to your **Plentymarkets back end**.
2. Open the section dedicated to **API or REST access**
3. Create or configure an API user/token with **read access** to products, categories, customers, and orders.
4. Copy the generated credentials (e.g. user, token/key, endpoint URL) from the configuration screen.

**Values to enter in the migration tool**

* **Endpoint/Server URL**, and the **user/token** pair.

</details>

<details>

<summary><strong>Printify</strong></summary>

1. Log in to **Printify**.
2. Open the account/store menu and choose **Connections**.
3. Scroll to the **API tokens** section.
4. Click **Generate** to create a new token.
5. Enter a name (e.g. “Migration Tool”) and select the scopes; for full migration, enable read access for shops, catalog, products, and orders.
6. Confirm to generate the token and copy it immediately.

**Values to enter in the migration tool**

* **API Token** – the Personal Access Token you generated.

</details>

<details>

<summary><strong>Quickbutik</strong></summary>

1. Sign in to the **Quickbutik control panel**.
2. Go to **Settings (Inställningar)** in the left menu.
3. At the bottom, in **Behind the shop (Bakom butiken)**, open the **API** block.
4. Click **+ Create new API key (+ Skapa ny API-nyckel)**.
5. Name the key (e.g. “Migration Tool”) and save changes.
6. Copy the **API Key** displayed (it’s only shown once) and store it safely.

**Values to enter in the migration tool**

* **API Key** – Quickbutik API key you just created.

</details>

<details>

<summary><strong>Salesforce</strong></summary>

1. Install **Salesforce CLI** following Salesforce’s official instructions.
2. Open a terminal/command prompt and run:\
   `sf org login web`
3. Log in via the browser window that opens and allow CLI access.
4. Back in the terminal, confirm the org is authorized.
5. Run:\
   `sf org display --target-org <your_username>` to display connection details.
6. Copy the **Access Token** and **Instance URL** from the output.

**Values to enter in the migration tool**

* **Access Token** – from CLI output.
* **Instance URL** – e.g. `https://yourdomain.my.salesforce.com`.

</details>

<details>

<summary><strong>ShopBase</strong></summary>

1. Log in to **ShopBase admin**.
2. Go to **Apps → Manage private apps**.
3. Click **Create a new private app**.
4. Enter an app name (e.g. “Next-Cart Migration Tool”) and an emergency developer email.
5. In **Admin API**, expand all permissions and assign **Read** (or Read/Write where necessary) to store content, customers, orders, products, themes, discounts, and inventory as required.
6. Save and confirm.
7. After saving, copy the generated **API Key** and **API Password** from the Admin API section.

**Values to enter in the migration tool**

* **Store URL** – your ShopBase admin URL (e.g. `https://xxxxxx.onshopbase.com`).
* **API Key**.
* **API Password**.

</details>

<details>

<summary><strong>Shopify</strong></summary>

1. Log into Shopify admin.
2. Go to **Settings → Apps and sales channels → Develop apps for your store**.
3. Create a new custom app (e.g., “Next-Cart Migration Tool”).
4. In **Admin API scopes**, enable **Read** access for Products, Orders, Customers, Collections, Pages, Blogs, etc.
5. Install the app on your store.
6. After installation, generate an **Admin API Access Token**.
7. Copy the token and your store’s **Admin URL** (e.g., `https://your-store.myshopify.com`).

**Fields to Use in Next-Cart**

* **Store Admin URL**
* **Admin API Access Token**

</details>

<details>

<summary><strong>ShopWired</strong></summary>

1. Log in to the **ShopWired admin**.
2. Open the section where **API Key and Secret** are managed (typically under account or integrations/settings).
3. Generate a new API key pair if one doesn’t exist, or locate the existing key and secret used for integrations.
4. Copy the **API Key** and **API Secret**.

**Values to enter in the migration tool**

* **API Key** – ShopWired API key.
* **API Secret** – corresponding secret.

</details>

<details>

<summary><strong>Square</strong></summary>

1. Open the Square authorization link provided by Next-Cart to install the [**Square Migration** app](https://shopping-cart-migration.next-cart.com/app/square/)
2. Log in to Square and grant access by clicking **Allow**.
3. After authorization, your **Square API Key** will be displayed (and can be downloaded).
4. Copy the key.

**Fields to Use in Next-Cart**

* **API Key**

</details>

<details>

<summary><strong>Squarespace</strong></summary>

1. Sign in to **Squarespace**.
2. Go to the **Developer/API** area from the site settings.
3. Create a **new API key / token** for data access.
4. Assign permissions that allow reading products, customers, and orders as needed.
5. Save and copy the generated **API Key** (and secret or token if provided).

**Values to enter in the migration tool**

* **API Key** (and any additional token/secret shown in your Squarespace guide).

</details>

<details>

<summary><strong>Storeden</strong></summary>

1. Log in to Storeden admin dashboard.
2. Go to **Settings → Remote access**.
3. Click **Generate API Key**.
4. Name the keyset (e.g., “Next-Cart Migration Tool”) and set access to **Read/Write** (or at least Read for migration).
5. Save; copy the **API Key** and **Exchange Key**.

**Fields to Use in Next-Cart**

* **API Key**
* **Exchange Key**

</details>

<details>

<summary><strong>Upgates</strong></summary>

1. Log into your Upgates administration.
2. Follow your internal “Create Upgates API Access” guide to:
   * Enable the API.
   * Generate API Username / Key or Token.
3. Ensure **Read** access is granted to relevant objects.
4. Copy the required credentials.

**Fields to Use in Next-Cart**

* **Store URL**
* **API Username / Key / Token**

</details>

<details>

<summary><strong>VTEX</strong></summary>

1. Log in to your **VTEX admin panel**.
2. Click the **Apps** icon and select **Application Keys**.
3. Click **Manage My Keys → Generate New**.
4. Enter a label for the key (e.g. “Migration”).
5. Add roles; for a full migration, assign a high-level role such as **Owner/Admin Super** or equivalent so all required data can be read.
6. Generate the key and copy the resulting **Application Key** and **Application Token** immediately (they are only shown once).

**Values to enter in the migration tool**

* **Store URL** – admin domain, e.g. `https://accountname.myvtex.com`.
* **Account Name** – the `accountname` part.
* **Application Key**.
* **Application Token**.

</details>

<details>

<summary>WIX</summary>

1. Log in to your Wix account.
2. Follow your **“How to Set Up Wix Connection”** doc to:
   * Identify the correct Site URL or Admin URL.
   * If required, add Wix app/integration that exposes API data.
3. Copy the connection details (URL, tokens, IDs) from Wix.
4. Use these values in the migration tool.

**Fields to Use in Next-Cart**

* **Site URL** / **Connection URL**
* **API Key** / **Token** (if present)

</details>

#### Verification

1. In the migration tool, run the connection test for the store that uses the API connection.
2. Confirm that the test completes without authentication or permission errors.
3. If the tool allows it, load a small preview of entities (for example, one product or order) to confirm data is accessible.
4. If errors appear:

* Re-check the credentials for typos.
* Confirm that the API key or app is enabled and has the necessary scopes.
* Confirm that any IP restrictions or rate limits are not blocking the request.
