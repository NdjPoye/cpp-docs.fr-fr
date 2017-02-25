---
title: "R&#233;f&#233;rence des mod&#232;les du fournisseur OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modèles du fournisseur OLE DB"
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# R&#233;f&#233;rence des mod&#232;les du fournisseur OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes et les interfaces des modèles de fournisseur OLE DB peuvent être regroupées selon les catégories suivantes.  Les documents de référence contiennent également des informations sur les [macros pour les modèles de fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Les classes utilisent la convention de dénomination suivante : une classe nommée avec le modèle **IWidgetImpl** fournirait une implémentation de l'interface **IWidget**.  
  
## Classes de Session  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Crée une nouvelle session à partir de l'objet source de données et retourne l'interface demandée sur la session nouvellement créée.  Interface forcée sur des objets de source de données.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Cette classe implémente les propriétés de session en appelant une fonction statique définie par le mappage de propriété.  Le mappage de propriété doit être spécifié dans votre classe session.  Interface obligatoire sur les sessions.  
  
## Classes d'ensemble de lignes  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Fournit une implémentation standard de l'ensemble de lignes OLE DB sans l'héritage multiple de nombreuses interfaces d'implémentation.  La seule méthode pour laquelle vous devez fournir l'implémentation est **Execute**.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 Fournit une implémentation par défaut du gestionnaire de ligne, utilisée dans la classe `IRowsetImpl`.  Un gestionnaire de ligne est logiquement une balise unique d'une ligne de sortie.  `IRowsetImpl` crée un nouveau `CSimpleRow` pour chaque ligne demandée dans `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB requiert que les fournisseurs implémentent **HACCESSOR**, qui est une balise vers un tableau de structures **DBBINDING**.  Fournit des **HACCESSOR** qui sont des adresses des structures de **BindType**.  Obligatoire sur les ensembles de lignes et des commandes.  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Délègue à une fonction statique définie par le mappage de colonnes du fournisseur.  Interface forcée sur les ensembles de lignes et les commandes.  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 Fournit des informations sur la disponibilité des conversions de type dans une commande ou sur un ensemble de lignes.  Forcé sur les commandes, les ensembles de lignes, et les ensembles de lignes d'index.  Implémente l'interface **IConvertTypeImpl** en déléguant à l'objet de conversion fourni par OLE DB.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Implémente l'interface **IDBSchemaRowset** et la fonction mise en modèle de créateur `CreateSchemaRowset`.  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Ouvre et renvoie un ensemble de lignes qui inclut toutes les lignes d'une table de base ou d'index.  Interface forcée pour un objet session.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 Implémente l'interface OLE DB [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx), qui permet de mettre à jour les valeurs des colonnes dans les lignes existantes, supprimer des lignes, puis insérer de nouvelles lignes.  
  
 [IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 Cette classe hérite de [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) et remplace [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  `IRowsetCreatorImpl` remplit les mêmes fonctions que `IObjectWithSite` mais possède également les propriétés OLE DB **DBPROPCANSCROLLBACKWARDS** et **DBPROPCANFETCHBACKWARDS**.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 Implémente l'interface **IRowsetIdentity**, qui vous permet de comparer si deux lignes de données sont identiques ou non.  
  
 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)  
 Fournit une implémentation de l'interface `IRowset`, qui est l'interface de base des ensembles de lignes.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 Implémente les propriétés d'ensemble de lignes à l'aide de mappage de propriété définie dans votre classe de commande.  Interface forcée sur les ensembles de lignes.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 Implémente l'interface OLE DB [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx), pour extraire des lignes aléatoires d'un ensemble de lignes.  Pour prendre en charge les signets OLE DB dans un ensemble de lignes, faites en sorte que l'ensemble de lignes hérite de cette classe.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Implémente des fonctions de diffusion pour informer les écouteurs sur le point de connexion **IID\_IRowsetNotify** des modifications apportées au contenu de l'ensemble de lignes.  Les consommateurs qui traite les notifications implémentent [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) et l'enregistrent sur ce point de connexion.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 Implémente l'interface OLE DB [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx), qui permet aux consommateurs de retarder la transmission des modifications apportées avec [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) à la source de données et pour annuler les modifications avant transmission.  
  
## Classes de Commande  
 [ICommandImpl](../../data/oledb/icommandimpl-class.md)  
 Fournit une implémentation de l'interface `ICommand`.  Cette interface n'est pas visible, mais est gérée par **ICommandTextImpl**.  Interface obligatoire sur l'objet de commande.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Cette implémentation de l'interface **ICommandProperties** est fournie par une fonction statique définie par la macro `BEGIN_PROPSET_MAP`.  Obligatoire sur les commandes.  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 Initialise, stocke, et retourne le texte de la commande.  Obligatoire sur les commandes.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Crée une nouvelle commande de l'objet session et retourne l'interface demandée sur la commande nouvellement créée.  Interface facultative sur des objets session.  
  
 D'autres classes de commande sont `IColumnsInfoImpl` et `IAccessorImpl`, décrites dans la section de classes ci\-dessus.  
  
## Les classes de sources de données  
 [IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)  
 Crée et supprime la connexion avec le consommateur.  Interface forcée sur les objets sources de données et interface facultative sur les énumérateurs.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` est une interface obligatoire pour les objets sources de données et une interface facultative pour les énumérateurs.  Toutefois, si un énumérateur expose **IDBInitialize**, il doit exposer `IDBProperties` \(définie sur la source de données\).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Obtient un pointeur d'interface sur l'objet source de données.  Interface forcée sur la session.  
  
## D'autres classes  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 Implémente les propriétés d'une série d'interfaces de propriétés OLE DB \(par exemple, `IDBProperties`, **ISessionProperties**, et `IRowsetInfo`\).  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 Implémente l'interface OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx), en ajoutant des enregistrements et l'extraction des enregistrements d'un membre de données.  
  
## Voir aussi  
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [modèles OLE DB](../../data/oledb/ole-db-templates.md)