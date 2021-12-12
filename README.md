# SupplyChainApp

This is Ethereum blockchain technology based Supply chain management decentralized application.

To test this project install Ganache and be sure to copy the addresses for A‐G from your own Ganache addresses at the beginning and throughout this file. If you use a text editor, you can do a Find and Replace to speed up this step.

A‐0: 0x1ECe02AB9324A9fBb0Db902285D1120D94B6E11B B‐1: 0x9BE09B31DA53811332604665164649Ba32d07378 C‐2: 0x3A39c396582c704292216D365d924237252888d2 D‐3: 0x08F04358a14c1819E77902d41DBa4AAD74185c2D E‐4: 0x1f08137ccc2d7E8D2EC4aEb63aE27FB031DA0650 F‐5: 0x0Eddd377bc1178A4D359D92bB7b3d1Fce9748E3E G‐6: 
0xc4E647ac83d17A09F1040c95E01c36BEb5aa1B23

supplyChain.deployed().then(function(instance) {return instance });

// Create 3 manufacturer participants (A, B, C) supplyChain.deployed().then(function(instance) {return instance.addParticipant("A","passA","0x1ECe02AB9324A9fBb0Db902285D1120D94B6E11B","Manufacturer") }); supplyChain.deployed().then(function(instance) {return instance.addParticipant("B","passB","0x9BE09B31DA53811332604665164649Ba32d07378","Manufacturer") }); supplyChain.deployed().then(function(instance) {return instance.addParticipant("C","passC","0x3A39c396582c704292216D365d924237252888d2","Manufacturer") });

// Create 2 supplier participants (D, E) supplyChain.deployed().then(function(instance) {return instance.addParticipant("D","passD","0x08F04358a14c1819E77902d41DBa4AAD74185c2D","Supplier") }); supplyChain.deployed().then(function(instance) {return instance.addParticipant("E","passE","0x1f08137ccc2d7E8D2EC4aEb63aE27FB031DA0650","Supplier") });

// Create 2 consumer participants (F, G) supplyChain.deployed().then(function(instance) {return instance.addParticipant("F","passF","0x0Eddd377bc1178A4D359D92bB7b3d1Fce9748E3E","Consumer") }); 
supplyChain.deployed().then(function(instance) {return instance.addParticipant("G","passG","0xc4E647ac83d17A09F1040c95E01c36BEb5aa1B23","Consumer") });

// Get participant details supplyChain.deployed().then(function(instance) {return instance.getParticipant(0)}); supplyChain.deployed().then(function(instance) {return instance.getParticipant(1)}); supplyChain.deployed().then(function(instance) {return instance.getParticipant(2)}); supplyChain.deployed().then(function(instance) {return instance.getParticipant(3)}); supplyChain.deployed().then(function(instance) {return instance.getParticipant(4)}); supplyChain.deployed().then(function(instance) {return instance.getParticipant(5)}); supplyChain.deployed().then(function(instance) {return instance.getParticipant(6)});

// Create 6 products 100, 101 (owned by A), 200, 201 (owned by B), 300, 301 (owned C)

supplyChain.deployed().then(function(instance) {return instance.addProduct(0, "ABC", "100", "123", 11) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(0, "DEF", "101", "456", 12) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(1, "GHI", "200", "789", 13, {from:"0x9BE09B31DA53811332604665164649Ba32d07378"}) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(1, "JKL", "201", "135", 14, {from:"0x9BE09B31DA53811332604665164649Ba32d07378"}) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(2, "MNO", "300", "357", 15, {from:"0x3A39c396582c704292216D365d924237252888d2"}) });

supplyChain.deployed().then(function(instance) {return instance.addProduct(2, "PQR", "301", "759", 16, {from:"0x3A39c396582c704292216D365d924237252888d2"}) });

// Get product details supplyChain.deployed().then(function(instance) {return instance.getProduct(0) }); supplyChain.deployed().then(function(instance) {return instance.getProduct(1) }); supplyChain.deployed().then(function(instance) {return instance.getProduct(2) }); supplyChain.deployed().then(function(instance) {return instance.getProduct(3) }); supplyChain.deployed().then(function(instance) {return instance.getProduct(4) }); supplyChain.deployed().then(function(instance) {return instance.getProduct(5) });

// Move products along supply chain: Manufacturer=> Supplier=> Supplier=> Consumer supplyChain.deployed().then(function(instance) {return instance.newOwner(0, 3, 0, {from: "0x1ECe02AB9324A9fBb0Db902285D1120D94B6E11B"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(1, 3, 3, {from: "0x9BE09B31DA53811332604665164649Ba32d07378"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(2, 3, 4, {from: "0x3A39c396582c704292216D365d924237252888d2"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(0, 3, 1, {from: "0x1ECe02AB9324A9fBb0Db902285D1120D94B6E11B"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(2, 4, 5, {from: "0x3A39c396582c704292216D365d924237252888d2"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(1, 4, 2, {from: "0x9BE09B31DA53811332604665164649Ba32d07378"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 6, 4, {from: "0x08F04358a14c1819E77902d41DBa4AAD74185c2D"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 4, 1, {from: "0x08F04358a14c1819E77902d41DBa4AAD74185c2D"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 4, 3, {from: "0x08F04358a14c1819E77902d41DBa4AAD74185c2D"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(4, 5, 2, {from: "0x1f08137ccc2d7E8D2EC4aEb63aE27FB031DA0650"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(3, 4, 0, {from: "0x08F04358a14c1819E77902d41DBa4AAD74185c2D"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(4, 6, 0, {from: "0x1f08137ccc2d7E8D2EC4aEb63aE27FB031DA0650"}) }); supplyChain.deployed().then(function(instance) {return instance.newOwner(4, 5, 3, {from: "0x1f08137ccc2d7E8D2EC4aEb63aE27FB031DA0650"}) });

supplyChain.deployed().then(function(instance) {return instance.getProvenance(0) }); supplyChain.deployed().then(function(instance) {return instance.getProvenance(1) }); supplyChain.deployed().then(function(instance) {return instance.getProvenance(2) }); supplyChain.deployed().then(function(instance) {return instance.getProvenance(3) }); supplyChain.deployed().then(function(instance) {return instance.getProvenance(4) }); supplyChain.deployed().then(function(instance) {return instance.getProvenance(5) });
