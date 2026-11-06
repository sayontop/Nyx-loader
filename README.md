# Nyx Loader

A personal Windows launcher for **Minecraft: Java Edition 1.21.4** on Fabric, made to start the Nyx client mod.

## What it does

- Launches a Fabric 1.21.4 install that the player already has, using the game files from their own Modrinth installation. The loader never downloads the game.
- Plays offline with a nickname, or signs in with a Microsoft account to use the player's own Minecraft profile.
- Has settings for RAM, window size and garbage collector, plus a page showing the state of the client files.

## Microsoft sign-in

- **How you sign in:** the loader uses the Microsoft identity platform's **device code flow**. You enter a short code at microsoft.com/link and sign in on Microsoft's own page. The loader never sees or stores a password.
- **What happens next:** the Microsoft token goes through Xbox Live and XSTS, then to `api.minecraftservices.com/authentication/login_with_xbox`. The Minecraft profile then comes from `/minecraft/profile`, and the game starts with that account.
- **What's stored:** the refresh token and the current Minecraft token, both encrypted with Windows DPAPI, so only the signed-in Windows user on that PC can read them.
- **Signing out:** deletes them.
- **Where tokens go:** only to Microsoft, Xbox Live and Minecraft services, then to the game when it starts. The loader collects no data of its own.

## Requirements

- Windows 10 or 11
- Minecraft: Java Edition, owned by the account you sign in with
- A Fabric 1.21.4 profile in the Modrinth App

## Contact

Open an issue on this repository.
