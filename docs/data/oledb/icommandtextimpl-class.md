---
title: "ICommandTextImpl, classe | Microsoft Docs"
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
  - "ICommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandText (classe)"
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandTextImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Chaque classe assure l'implémentation pour [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) interface.  
  
## Syntaxe  
  
```  
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### Paramètres  
 `T`  
 La classe de commande dérivée de **ICommandTextImpl**.  
  
## Membres  
  
### Methodes d'interface  
  
|||  
|-|-|  
|[ObtenirTexteCommande](../../data/oledb/icommandtextimpl-getcommandtext.md)|Retourne la commande de texte défini par le dernier appel à [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|  
|[EnsembleTexteCommande](../../data/oledb/icommandtextimpl-setcommandtext.md)|Définit le texte de la commande, en remplaçant le texte de la commande existante.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_strTexteCommande](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|Stocke le texte de commande.|  
  
## Notes  
 Interface forcée sur les commandes.  
  
## Configuration requise  
 **En\-tête :** altdb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)