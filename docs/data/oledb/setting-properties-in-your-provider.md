---
title: "D&#233;finition de propri&#233;t&#233;s dans votre fournisseur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fournisseurs OLE DB, propriétés"
  - "propriétés (C++), fournisseur OLE DB"
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# D&#233;finition de propri&#233;t&#233;s dans votre fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherchez le groupe de propriétés et l'ID de propriété de la propriété qui vous intéresse.  Pour plus d'informations, consultez [Propriétés OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) dans *OLE DB Programmer's Reference*.  
  
 Dans le code du fournisseur généré par l'Assistant, recherchez le mappage des propriétés correspondant au groupe de propriétés.  Le nom du groupe de propriétés correspond généralement au nom de l'objet.  Les propriétés command et rowset se trouvent dans la commande ou le rowset ; les propriétés source de données et initialisation se trouvent dans l'objet data source.  
  
 Dans le mappage des propriétés, ajoutez une macro [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  PROPERTY\_INFO\_ENTRY\_EX prend quatre paramètres :  
  
-   L'ID de propriété correspondant à votre propriété.  Vous devez supprimer les sept premiers caractères \(« DBPROP\_ »\) placés à gauche du nom de la propriété.  Par exemple, si vous souhaitez ajouter **DBPROP\_MAXROWS**, passez `MAXROWS` en tant que premier élément.  S'il s'agit d'une propriété personnalisée, passez le nom GUID complet \(par exemple, `DBMYPROP_MYPROPERTY`\).  
  
-   Le type variant de la propriété \([Propriétés OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) dans *OLE DB Programmer's Reference*\).  Entrez le type **VT\_** \(tel que `VT_BOOL` ou `VT_I2`\) correspondant au type de données.  
  
-   Des indicateurs pour signaler si la propriété est accessible en lecture et écriture et le groupe auquel elle appartient.  Par exemple, le code suivant indique une propriété accessible en lecture\/écriture appartenant au groupe rowset :  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   La valeur de base de la propriété.  Il peut s'agir de **VARIANT\_FALSE** pour un type booléen ou zéro pour un type entier, par exemple.  La propriété a cette valeur, sauf si elle est modifiée.  
  
    > [!NOTE]
    >  Certaines propriétés sont raccordées ou chaînées à d'autres propriétés, telles que les signets ou la mise à jour.  Quand un consommateur affecte à une propriété la valeur true, une autre propriété peut également être définie.  Les modèles du fournisseur OLE DB prennent cette fonction en charge par le biais de la méthode [CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).  
  
## Propriétés non prises en compte par les fournisseurs OLE DB Microsoft  
 Les fournisseurs OLE DB Microsoft ignorent les propriétés OLE DB suivantes :  
  
-   **DBPROP\_MAXROWS** fonctionne uniquement pour les fournisseurs en lecture seule \(c'est\-à\-dire, là où DBPROP\_IRowsetChange et DBPROP\_IRowsetUpdate ont une valeur false\) ; dans les autres cas, cette propriété n'est pas prise en charge.  
  
-   **DBPROP\_MAXPENDINGROWS** est ignorée ; le fournisseur spécifie sa propre limite.  
  
-   **DBPROP\_MAXOPENROWS** est ignorée ; le fournisseur spécifie sa propre limite.  
  
-   **DBPROP\_CANHOLDROWS** est ignorée ; le fournisseur spécifie sa propre limite.  
  
## Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)