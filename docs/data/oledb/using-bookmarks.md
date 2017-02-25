---
title: "Utilisation des signets | Microsoft Docs"
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
  - "signets, OLE DB"
  - "modèles du fournisseur OLE DB, signets"
  - "fournisseurs OLE DB, prise en charge des signets"
  - "jeux de lignes, signets"
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation des signets
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avant d'ouvrir le jeu de ligne, vous devez indiquer au fournisseur que vous souhaitez utiliser des signets.  Pour ce faire, affectez à la propriété **DBPROP\_BOOKMARKS** la valeur **true** dans votre jeu de propriétés.  Le fournisseur récupère des signets comme colonne zéro, donc vous devez utiliser la macro spéciale `BOOKMARK_ENTRY` et la classe `CBookmark` si vous utilisez un accesseur statique.  `CBookmark` est une classe de modèle où l'argument est la longueur en octets de la mémoire tampon de signet.  La taille de la mémoire tampon requise pour un signet dépend du fournisseur.  Si vous utilisez le fournisseur OLE DB ODBC, comme le montre l'exemple suivant, la mémoire tampon doit avoir une capacité de 4 octets.  
  
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
  
 Si vous utilisez `CDynamicAccessor`, la mémoire tampon est affectée dynamiquement au moment de l'exécution.  En ce cas, vous pouvez utiliser une version spécialisée de `CBookmark` pour laquelle vous ne spécifiez pas une taille de mémoire tampon.  Utilisez la fonction `GetBookmark` pour récupérer le signet de l'enregistrement en cours, comme indiqué dans cet exemple de code :  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
product.Open(session, "Products", &propset);  
product.MoveNext();  
product.GetBookmark(&bookmark);  
```  
  
 Pour plus d'informations sur la prise en charge des signets par les fournisseurs, consultez [Prise en charge des signets par le fournisseur](../../data/oledb/provider-support-for-bookmarks.md).  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)