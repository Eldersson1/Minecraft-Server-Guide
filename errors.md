## Errors

Every Minecraft server owner hits errors and that’s normal. Whether it’s a plugin throwing red text all over your console or players getting random disconnects, most problems aren’t the end of the world. You just need to know **why** they happen and how to track them down.

### Understanding the Source

Not all errors come from the same place. The key is to figure out **where the issue starts** before trying random fixes.

Here’s a quick breakdown:
- **Plugin errors:** Usually caused by version mismatches, missing dependencies, or conflicting plugins.  
- **Server errors:** Often tied to outdated JAR files, bad configurations, or low memory.  
- **Player errors:** Can happen from corrupted worlds, resource packs, or bad client versions.  
- **Network errors:** Result from port forwarding mistakes, firewall blocks, or unstable internet connections.

Start by reading the **console logs** carefully. The first red line that appears is often the real cause — not the 10 lines after it.

---

### Common Errors and Fixes

**1. “Unknown command”**  
→ You probably typed the command wrong or the plugin providing that command didn’t load.  
*Fix:* Check if the plugin is in your `/plugins` folder and shows up as enabled on startup.

**2. “Could not pass event to plugin”**  
→ The plugin threw an error during an event (like a player joining).  
*Fix:* Check your plugin versions — one of them likely isn’t compatible with your current server JAR.

**3. “OutOfMemoryError” or “Server is overloaded”**  
→ Your server doesn’t have enough RAM or CPU power.  
*Fix:* Reduce view distance, limit plugins, or upgrade hosting resources.

**4. “Internal Exception: java.io.IOException”**  
→ Usually caused by unstable connections or too many players for the server’s capacity.  
*Fix:* Check your internet, restart the server, or raise connection timeouts.

**5. “World can’t be loaded”**  
→ The world files are corrupted or named incorrectly.  
*Fix:* Rename or restore from a backup. Always keep regular backups of worlds.

---

### Connection Errors (The Most Common Ones)

These are the ones that stop people from joining at all. If your console says “server is running,” but no one can connect, it’s usually one of these.

**1. “Can’t connect to server” or “Connection refused: connect”**  
→ Your **port isn’t open** or your router isn’t forwarding correctly.  
*Fix:*  
- Make sure your **server.properties** port is set to `25565` (or your chosen one).  
- Log into your router and **port forward TCP/UDP 25565** to your PC’s local IP address.  
- If using a VPN, disable it or allow port forwarding inside it.

**2. “Timed out” or “Disconnected” immediately**  
→ The connection reached your router but didn’t reach the server.  
*Fix:*  
- Check your **firewall or antivirus** — they often block incoming connections.  
- Ensure the server is actually running and not crashing on startup.  
- Verify that your **IP hasn’t changed** (local IPs often reset after reboot; set it static).

**3. “No further information”**  
→ Generic message when the client can’t find the server.  
*Fix:*  
- Try connecting with your **local IP** (`192.168.x.x`) if you’re on the same network.  
- Use **your public IP** (`whatismyip.com`) for outside players.  
- If you’re using a dynamic IP, consider a **free DNS** service like No-IP.

**4. “Internal Exception: java.net.SocketException: Connection reset”**  
→ Usually bad internet, lag spikes, or overloaded network hardware.  
*Fix:*  
- Restart your router or try a wired connection.  
- Lower player slots or reduce plugin load if your CPU is spiking.

**5. “Failed to connect to server: Outdated server/client”**  
→ You and the server are on different Minecraft versions.  
*Fix:*  
- Check your server version in console startup logs.  
- Match your client version or install a version-compatible plugin (like ViaVersion).

---

### Debugging Smartly

When debugging, **change one thing at a time.**  
Restart the server after each tweak so you actually see what fixed (or broke) it. Randomly editing configs and deleting things usually makes it worse.

If you’re stuck, simplify:
- Remove half your plugins and test again.  
- Swap to a fresh world temporarily.  
- Run the server locally to isolate hosting issues.

You’ll almost always find the cause faster when you isolate the problem instead of chasing every symptom.

---

Errors aren’t failures, they’re just clues. Once you get used to reading logs and understanding what the console’s trying to tell you, debugging becomes less “panic” and more “detective work.”
