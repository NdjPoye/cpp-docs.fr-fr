---
title: "Substitution des services par d&#233;faut du fournisseur | Microsoft Docs"
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
  - "services OLE DB, substituer les méthodes par défaut"
  - "fournisseurs de services (OLE DB)"
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Substitution des services par d&#233;faut du fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La valeur de Registre du fournisseur pour les **OLEDB\_SERVICES** est retournée en tant que valeur par défaut pour la propriété d'initialisation [DBPROP\_INIT\_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx) sur l'objet data source.  
  
 Tant que l'entrée du Registre existe, les objets du fournisseur sont regroupés et l'utilisateur peut substituer le paramétrage par défaut des services activés en définissant la propriété **DBPROP\_INIT\_OLEDBSERVICES** avant l'initialisation.  Pour activer ou désactiver un service particulier, l'utilisateur peut obtenir généralement la valeur actuelle de la propriété **DBPROP\_INIT\_OLEDBSERVICES**, définir ou supprimer le bit correspondant à la propriété particulière à activer ou à désactiver, et rétablir la propriété.  Il est possible de définir directement **DBPROP\_INIT\_OLEDBSERVICES** dans OLE DB, ou dans la chaîne de connexion passée à ADO ou à **IDataInitialize::GetDatasource**.  Les valeurs correspondantes pour activer\/désactiver des services particuliers sont répertoriées dans le tableau suivant :  
  
|Services activés par défaut|Valeur de propriété DBPROP\_INIT\_OLEDBSERVICES|Valeur dans la chaîne de connexion|  
|---------------------------------|-----------------------------------------------------|----------------------------------------|  
|Tous les services \(par défaut\)|**DBPROPVAL\_OS\_ENABLEALL**|"Services OLE DB \= \-1;"|  
|Tous sauf le regroupement et l'inscription automatique|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT**|"Services OLE DB \= \-4;"|  
|Tous sauf le curseur client|**DBPROPVAL\_OS\_ENABLEALL** &<br /><br /> ~**DBPROPVAL\_OS\_CLIENTCURSOR**|"Services OLE DB \= \-5;"|  
|Tous sauf le regroupement, l'inscription automatique et le curseur client|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT &**<br /><br /> **~DBPROPVAL\_OS\_CLIENTCURSOR**|"Services OLE DB \= \-7;"|  
|Pas de services|~**DBPROPVAL\_OS\_ENABLEALL**|"Services OLE DB \= 0;"|  
  
 Si l'entrée du Registre n'existe pas pour le fournisseur, les gestionnaires de composants ne regroupent pas les objets du fournisseur, et aucun service n'est appelé, même quand il est demandé explicitement par l'utilisateur.  
  
## Voir aussi  
 [Resource Pooling](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [How Consumers Use Resource Pooling](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [How Providers Work Effectively with Resource Pooling](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [Activation et désactivation des services OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)