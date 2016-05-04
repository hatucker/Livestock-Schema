#Livestock Schema
##*Transaction*

|Attribute|Datatype|Required|Reference|Note|
|---------|--------|--------|---------|----|
Livestock.Transactions.TransactionType||Y|Stock Reconciliation B4|Review these - FarmIQ is using different items such as AnimalInternalMove (move between paddocks)
Livestock.Transactions.TransactionId||Y|Stock Reconciliation A|Internal to source system
Livestock.Transactions.dateOfTransaction|Date|Y|Stock Reconciliation|Note that FarmIQ are using ISO 8601 basic format; they should probably use the separator format (not a big deal).
Livestock.Transactions.OtherParty[]||Y||Array of Organizations
Livestock.Transactions.Lines[]||Y||Array of Transaction Item
Livestock.Transaction Item.SpeciesSimpleName|String|Y|Stock Reconciliation B1|Confirm set of valid values from standard
Livestock.Transaction Item.Sex|String|Y|Stock Reconciliation A|Confirm set of valid values from standard
Livestock.Transaction Item.FertilityStatus|String|Y|Stock Reconciliation B3|Confirm set of valid values from standard
Livestock.Transaction Item.BreedAssessed|String|Y|Stock Reconciliation A|Need a master lookup list on Standards web site
Livestock.Transaction Item.EnterpriseUse[]|Set|Y|Stock Reconciliation A|"Set: current values are: [Capital| Trading| Genetics| Dairy] - stock tends to be capital or trading or genetics and may also be dairy (or not) - could add Meat| Fibre
Livestock.Transaction Item.SeasonBorn|Number|Y|Stock Reconciliation A|
Livestock.Transaction Item.GroupName|String||Animals A4|Internal Name for group in source system
Livestock.Transaction Item.GroupID|String|||Internal ID for group in source system
Livestock.Transaction Item.Paddock|String|||"Only really needed to support AnimalInternalMove| which is not really a stock transaction
Livestock.Transaction Item.Quantity|Number|Y|Stock Reconciliation A|
Livestock.Transaction Item.MeanWeight|Number||Animals B1|
Livestock.Transaction Item.value|Number||Stock Reconciliation A|
Livestock.Transaction Item.reproductiveStatus|String||Stock Reconciliation B2|Add this
Livestock.Transaction Item.birthDate|Date||Stock Reconciliation A|Add this
Livestock.Transaction Item.birthDateConfidence|String||Stock Reconciliation A|Add this
Livestock.Transaction Item.ID|String||Animal 3.1|Array of animal ID's Note inidivdual animal data could be delivered as a separate schema to allow for different licence terms.
Livestock.Organization.name|||schema.org|
Livestock.Organization.url|||schema.org|
Livestock.Organization.description|||schema.org|
Livestock.Organization.isicv4|||schema.org|"International Standard Industrial Classification: 0141 = cattle farming| 0144 = sheep farming| 0150 = mixed farming| 1010 = meat processing| 4610 = livestock auction/trader
Livestock.Organization.geo|||schema.org|
Livestock.Organization.globalLocationNumber|||schema.org|Equates to NZBN
Livestock.Organization.contactPoint[]|||schema.org|Array of contact points
Livestock.Organization.identifier[]|||Animals 3|Array of URN Herd/Flock/NAIT codes for the organisation
Livestock.ContactPoint.telephone|||schema.org|
Livestock.ContactPoint.email|||schema.org|
Livestock.ContactPoint.address|||schema.org|
Livestock.ContactPoint.contactType|||schema.org|
Livestock.currentBalance.lines[]||||Array of Transaction Items Means AFTER this transaction data
