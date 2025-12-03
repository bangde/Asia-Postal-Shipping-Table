=== Asia Postal & Table Rate Shipping ===
Contributors: sjconsultinggroup
Tags: woocommerce, shipping, table rate, asia, postal, ems, shipping zones
Requires at least: 5.6
Tested up to: 6.4
Stable tag: 2.3.2
Requires PHP: 7.4
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

A specialized WooCommerce shipping method for Asian Postal Carriers (Japan Post, Thai Post, China Post, etc.) featuring a powerful tree-table rate logic engine.

== Description ==

Asia Postal & Table Rate Shipping is the ultimate solution for WooCommerce stores shipping from or within Asia. Unlike generic table rate plugins, this tool is built specifically to handle the complex weight tiers, zoning, and volumetric logic used by national postal carriers like Japan Post, Thailand Post, China Post, and more.

It replaces complex coding with a simple, logic-based table that allows you to define rules based on Weight, Cart Total, Item Quantity, and Shipping Class.

🚀 Key Features

🔃 Drag-and-Drop Reordering: Easily prioritize your rules by dragging rows up or down. Essential for complex logic stacks (First Match Wins).

⚡ Quick Duplicate: Clone existing rules with one click to speed up data entry for tiered pricing.

🌏 Extensive Carrier Support: Pre-configured zone presets for 19+ major Asian carriers including Thailand Post, Japan Post, China Post, SingPost, Pos Malaysia, India Post, and many more.

🎛️ Service Selector: Don't just load "Zones"—load specific services. Choose between EMS, ePacket, Surface Mail, or International Parcel presets for supported carriers.

📂 External Zone Database: Carrier zones are stored in a separate zones.json file, making it easy to update definitions without touching code.

📦 Tracking Link Generator: Automatically generate tracking links for orders based on carrier patterns (e.g., https://track.carrier.com?id={tracking_number}). Admin tool included on the Order Edit page.

📍 Postcode & Zip Code Filtering: Target specific remote areas, islands, or provinces using exact codes (e.g., 10001), wildcards (90*), or ranges (1000...2000).

⚖️ Weight Step Rounding: Mimic postal counter pricing by rounding up weights to the nearest step (e.g., round 1.1kg up to 1.5kg).

⚖️ Tiered Weight Logic: Accurately calculate postal rates using "Base Weight" logic (e.g., "First 1kg is $20, every additional 1kg is $5").

📦 Volumetric (Dimensional) Weight: Protect your margins by automatically calculating volumetric weight (Divisor 5000 or 6000) and charging for whichever is higher.

🏷️ Shipping Class Support: Create specific rules for "Heavy" or "Fragile" items that override standard rates.

🔄 CSV Import / Export: Manage hundreds of rules easily in Excel and import them in seconds. Perfect for backups or bulk edits.

🖼️ Brand Icons: Auto-detects carrier logos from the /icons/ folder or allows custom icon URLs for a professional checkout experience.

🛠️ Debug Mode: Troubleshoot your rules easily with admin-only logs on the cart page.

🌏 Supported Presets

Thailand Post: EMS World, ePacket.

Japan Post: EMS, International Parcel.

China Post: Air Parcel Groups.

Singapore Post: Speedpost Standard.

Hong Kong Post: Speedpost.

Pos Malaysia: International Air Mail.

India Post: International Air Parcel.

Pos Indonesia: EMS International.

And generic support for 10+ others.

== Installation ==

Upload the asia-post-shipping folder to the /wp-content/plugins/ directory.

Important: Ensure the icons folder and zones.json file are present inside the plugin folder.

Activate the plugin through the 'Plugins' menu in WordPress.

Go to WooCommerce > Settings > Shipping.

Add a Shipping Zone (e.g., "Global" or "Asia").

Click Add Shipping Method and select Asia Post / Table Rate.

Click Edit to configure your rates and carrier branding.

== Frequently Asked Questions ==

= How do I prioritize rules? =
The plugin processes rules from Top to Bottom. The first rule that matches the cart conditions "wins" (unless "Show All Rates" is enabled). You can use the drag handle on the left of each row to reorder them instantly.

= How do I use the Service Selector? =

Select a carrier (e.g., "Thailand Post").

A second dropdown will appear next to the "Load Zones" button.

Select the specific service (e.g., "ePacket").

Click "Load Zones". The table will fill with the specific tiers/zones for ePacket.

= Can I add my own Zone Presets? =
Yes! The plugin now uses a zones.json file located in the plugin directory. You can edit this file to add your own carrier definitions or update existing zones without touching the PHP code.

= What is the "Calculation Mode"? =
This setting controls how the plugin selects rates:

Single Best Match: Stops as soon as it finds the first valid rule. Use this if you want the plugin to make the decision for the customer.

Show All Matching Rates: Continues checking all rules. If a customer qualifies for EMS, ePacket, and Surface Mail, all three options will be displayed at checkout.

= How does the "Base Weight" logic work? =
This is designed for postal rates.

Base Cost: The price for the first X kg.

Base Weight: The X kg included in the base price.

Cost Per Kg: The price for every kg after the base weight.

Formula: Total Cost = Base Cost + ( Per Kg * ( Total Weight - Base Weight ) )

= My shipping rates aren't showing up! =

Go to the plugin settings and enable Debug Mode.

Go to your Cart page (as an admin).

You will see a blue notice explaining exactly why a rule passed or failed.

== Screenshots ==

Main Interface: Clean, table-based layout for managing shipping rules.

Service Selector: Choosing between EMS and ePacket for Thailand Post.

Checkout Experience: Displaying carrier icons next to shipping rates.

== Changelog ==

= 2.3.2 =

Fix: Resolved JS ID conflict for "Load Zones" button on installations with multiple shipping zones.

Optimization: Cleaned up dead JS code for faster loading.

= 2.3.1 =

UX: "Delete Selected" button now automatically hides when no rules exist.

= 2.3.0 =

Feature: Added Bulk Delete functionality (checkboxes and "Delete Selected" button).

= 2.2.2 =

UI: Fixed wrapping issue for Duplicate/Delete icons on smaller screens.

= 2.2.1 =

UI: Added Row Numbers (#1, #2) for easier tracking.

UI: Optimized column widths for Country, Base Weight, and Qty.

UI: Renamed "B" to "Base ($)" and "K" to "+ /kg ($)" for clarity.

= 2.2.0 =

Feature: Added Drag-and-Drop reordering for shipping rules.

Feature: Added "Duplicate Rule" button (copy icon) for faster data entry.

UI: Implemented Sticky Headers for the rules table to keep columns visible while scrolling.

= 2.1.0 =

Architecture: Moved zone definitions to an external zones.json file for easier maintenance and updates.

Update: Refactored PHP to load presets dynamically from the JSON file.

= 2.0.0 =

Feature: Added "Service Selector" dropdown. Users can now choose specific sub-services (e.g., EMS vs ePacket) when loading presets.

Data: Added comprehensive zone data for Japan Post, China Post, SingPost, Hong Kong Post, Pos Malaysia, India Post, and Pos Indonesia.

= 1.9.0 =

Feature: Added "Calculation Mode" setting (Single Best Match vs. Show All Rates).

= 1.8.3 =

Fix: Moved Import Form to footer to prevent nested form HTML conflicts.

= 1.8.0 =

Feature: Added "Item Quantity" (Min/Max) condition.

= 1.7.0 =

Feature: Added Tracking Link Generator.

= 1.6.1 =

Security: Hardened data sanitization and CSV validation.

= 1.6.0 =

Feature: Added Weight Rounding Step and Postcode filtering.

= 1.5.4 =

UI Improvement: Simplified table headers and added currency symbols to input labels for better clarity.

= 1.5.3 =

UI Improvement: Renamed "B" and "K" fields to "Base" and "+ /kg" for better readability.

= 1.5.2 =

Fix: Updated dropdown text to say "Province/State" to match table headers.

= 1.5.1 =

UX: Added helpful tooltips to Load, Export, and Import buttons.

= 1.5.0 =

Feature: Added "Load Standard Zones" button for one-click setup of carrier presets (starting with Thai Post).

= 1.4.2 =

Feature: Auto-detection of carrier icons from the /icons/ folder.

= 1.4.0 =

Feature: Added Shipping Class support for complex product mixes.

= 1.3.0 =

Feature: Added CSV Import/Export functionality for bulk management.

= 1.2.0 =

Feature: Added Volumetric Weight calculation.

Feature: Added Debug Mode for troubleshooting.

= 1.0.0 =

Initial Release.
