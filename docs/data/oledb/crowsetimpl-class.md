---
title: "CRowsetImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl"
  - "ATL.CRowsetImpl"
  - "ATL::CRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRowsetImpl (classe)"
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation standard de l'ensemble de lignes OLE DB sans l'héritage multiple de nombreuses interfaces d'implémentation.  
  
## Syntaxe  
  
```  
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl < T, IRowset >   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### Paramètres  
 `T`  
 Créez une classe qui dérive de `CRowsetImpl`.  
  
 `Storage`  
 Enregistrement utilisateur  
  
 `CreatorClass`  
 La classe qui contient les propriétés de l'ensemble de lignes ; en général la commande.  
  
 `ArrayType`  
 La classe qui sera comme stockage des données de l'ensemble de lignes.  Ce paramètre par défaut est `CAtlArray`, mais il peut être n'importe quelle classe qui prend en charge les fonctionnalités requises.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|Extrait une chaîne de **DBID** et la copie sur `bstr` transmis.|  
|[EnsembleTexteCommande](../../data/oledb/crowsetimpl-setcommandtext.md)|Valide et stocke **DBID**s dans les deux chaînes \([m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\).|  
  
### Méthodes substituables  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|Récupère les informations de colonne pour une demande d'un client particulière.|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|Vérifie si l'un ou l'autre ou les deux paramètres contiennent des valeurs de chaîne et, le cas échéant, copie les valeurs de chaîne aux membres de données [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|Vérifie si l'un ou l'autre ou les deux **DBID**s contiennent des valeurs de chaîne et, le cas échéant, les copier ses membres de données [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|Par défaut, `CAtlArray` qui créé un modèle sur l'argument TEMPLATE enregistré de l'utilisateur à `CRowsetImpl`.  Une classe de type tableau peut être utilisée en modifiant l'argument TEMPLATE d'`ArrayType` à `CRowsetImpl`.|  
|[m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|Contient la commande initiale de l'ensemble de lignes.|  
|[m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|Contient l'index initial de l'ensemble de lignes.|  
  
## Notes  
 `CRowsetImpl` fournit les substitutions sous la forme d'upcasts statiques.  Les méthodes contrôlent la manière dont un ensemble de lignes donné validera le texte de la commande.  Vous pouvez créer votre propre classe du style de `CRowsetImpl`lors de les interfaces d'implémentation plusieurs héritées.  La seule méthode pour laquelle vous devez fournir l'implémentation est **Exécuter**.  Selon le type d'ensemble de lignes, vous créez les méthodes de créateur attendront des signatures pour **Exécuter**.  Par exemple, si vous utilisez `CRowsetImpl`\- classe dérivée à implémenter un ensemble de lignes de schéma, la méthode de **Exécuter** aura la signature suivante :  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 Si vous créez `CRowsetImpl`\- classe dérivée à implémenter un ensemble de lignes de commande ou de session, la méthode de **Exécuter** aura la signature suivante :  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 Pour implémenter `CRowsetImpl`l'un des \- les méthodes dérivées de **Exécuter**, vous devez remplir des tampons de données internes \([m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)\).  
  
## Configuration requise  
 **En\-tête :** atldb.h