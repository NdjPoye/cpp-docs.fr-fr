---
title: "À l’aide de signets | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 41c8e5a44130eebfddc9e99ab7ef815b6e8e43a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-bookmarks"></a>Utilisation des signets
Avant d’ouvrir l’ensemble de lignes, vous devez indiquer au fournisseur que vous souhaitez utiliser des signets. Pour ce faire, définissez la **DBPROP_BOOKMARKS** propriété **true** dans votre jeu. Le fournisseur récupère les signets en tant que colonne zéro, vous devez utiliser la macro spéciale `BOOKMARK_ENTRY` et `CBookmark` si vous utilisez un accesseur statique de classe. `CBookmark`est une classe de modèle où l’argument est la longueur en octets de la mémoire tampon de signet. La longueur de la mémoire tampon requise pour un signet dépend du fournisseur. Si vous utilisez le fournisseur OLE DB pour ODBC, comme indiqué dans l’exemple suivant, la mémoire tampon doit être de 4 octets.  
  
```  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
  
CTable<CAccessor<CProducts> > product;  
product.Open(session, "Products", &propset);  
```  
  
 Si vous utilisez `CDynamicAccessor`, la mémoire tampon est affectée dynamiquement au moment de l’exécution. Dans ce cas, vous pouvez utiliser une version spécialisée de `CBookmark` pour laquelle vous ne spécifiez pas une longueur de la mémoire tampon. Utilisez la fonction `GetBookmark` pour récupérer le signet de l’enregistrement actuel, comme indiqué dans cet exemple de code :  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
product.Open(session, "Products", &propset);  
product.MoveNext();  
product.GetBookmark(&bookmark);  
```  
  
 Pour plus d’informations sur la prise en charge des signets dans les fournisseurs, consultez [prise en charge du fournisseur pour les signets](../../data/oledb/provider-support-for-bookmarks.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)