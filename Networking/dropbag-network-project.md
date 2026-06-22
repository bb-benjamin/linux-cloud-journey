# DropBag — Network Architecture Project

**By Benjamin Botchway | Networking Fundamentals | June 2026**

**Scenario:** A startup company wants to understand how their app is accessible globally.

---

## The Startup: DropBag

DropBag is a startup that lets travellers hire someone local to store their luggage for a few hours. You land in Accra, your hotel room is not ready, and you just need somewhere safe to drop your bags. You open the DropBag app and find a host three streets away. That is the product. Now let us talk about how the network that powers it actually works.

---

## The Internet — Three Users, One App

At the very top you see three users. One is in Lagos, one is in London, one is in Jakarta. All three are opening the DropBag app at the same time, from completely different parts of the world. The whole point of this architecture is to make that work seamlessly for all of them.

---

## DNS — The Internet's Address Book

When the Lagos user types dropbag.app into their phone, their phone does not actually know where that is. It asks DNS, which works like a phone book. The phone book looks up "DropBag" and replies: "That is at address 104.21.45.78. Go there." This entire lookup takes under half a second. Without DNS, you would have to memorise a number instead of a name.

---

## Firewall (First One) — The Front Door Bouncer

Before any traffic can get inside DropBag's network, it must pass a security check. The firewall has one rule: only secure, encrypted traffic is allowed. If someone tries to sneak in on any other channel, the door is shut in their face. Think of it as a nightclub bouncer with a very short list.

---

## Load Balancer — The Traffic Director

Once traffic clears the first firewall, it hits the load balancer. DropBag runs three app servers, and the load balancer's job is to spread requests evenly across all three so no single server gets overwhelmed. If it is a normal Tuesday, all three servers share the work calmly. If a travel influencer posts about DropBag and ten thousand people sign up in an hour, the load balancer can spin up extra servers automatically. And if one server develops a fault, the load balancer quietly stops sending it traffic — most users never notice.

---

## App Servers — The Kitchen

The app servers are where the actual work happens. When you search for a bag storage host near you, an app server processes that request, figures out what you need, asks the database for nearby hosts, and sends the answer back to your phone. They are the chefs in the kitchen — the users never see them, but they do all the cooking.

---

## Firewall (Second One) — Inner Vault Door

There is a second firewall between the app servers and the database. Even if an attacker somehow got past the first firewall and reached an app server, they would hit a second locked door before touching any customer data. Only the app servers have a key. Nobody else even knows the vault exists.

---

## Database — The Vault

This is where all of DropBag's customer data lives. Names, booking history, payment references, host ratings. It sits completely hidden from the outside internet. The only things that can talk to it are the app servers, and only when they have a legitimate reason to.

---

## The Staff-Only Zone

At the bottom sit three internal tools. The NAT gateway lets the servers reach the internet when they need to download a software update — but it hides the server's real address while doing so. The admin dashboard is where the DropBag team can manage users and listings. And monitoring runs health checks every 30 seconds on every server, so the team gets an alert the moment anything looks wrong.

---

## The Result

Our Lagos user, London user, and Jakarta user all get a fast, secure, reliable response — and none of them has any idea this whole system is running behind the scenes. That is exactly how good infrastructure should feel: completely invisible.

---

*This project was built as part of study on Networking Fundamentals, covering IP addressing, DNS, HTTP/HTTPS, Firewalls, NAT, and Load Balancing.*
