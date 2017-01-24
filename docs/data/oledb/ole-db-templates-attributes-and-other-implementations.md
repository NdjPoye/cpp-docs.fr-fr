---
title: "Mod&#232;les, attributs et autres impl&#233;mentations OLE&#160;DB | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modèles OLE DB"
  - "modèles OLE DB, à propos des modèles OLE DB"
  - "OLE DB, implémentations"
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mod&#232;les, attributs et autres impl&#233;mentations OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Modèles OLE DB ATL  
 Les modèles OLE DB, qui font partie d'ATL \(Active Template Library\), facilitent l'utilisation de la technologie performante des bases de données OLE DB en fournissant des classes qui implémentent un grand nombre d'interfaces OLE DB courantes.  À cette bibliothèque de modèles s'ajoute une prise en charge de type Assistant pour la création d'applications de départ OLE DB.  
  
 Cette bibliothèque de modèles se divise en deux parties :  
  
-   **Modèles du consommateur OLE DB** Permettent d'implémenter une application de type client \(consommateur\) OLE DB.  
  
-   **Modèles du fournisseur OLE DB** Permettent d'implémenter une application de type serveur \(fournisseur\) OLE DB.  
  
 Pour utiliser les modèles OLE DB, vous devez connaître les modèles C\+\+, COM et les interfaces OLE DB.  Si vous n'êtes pas familiarisé avec OLE DB, consultez le [Guide de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx).  
  
 Pour plus d'informations, vous pouvez :  
  
-   lire les rubriques relatives aux [modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md) ou aux [modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md) ;  
  
-   créer un [consommateur OLE DB](../../data/oledb/creating-an-ole-db-consumer.md) ou un [fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md) ;  
  
-   consulter la liste des [classes du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) ou des [classes du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-reference.md) ;  
  
-   consulter la liste des [exemples de modèles OLE DB](http://msdn.microsoft.com/fr-fr/08958863-0b5f-41ad-ae99-fca7440c553c) ;  
  
-   Consultez le [Guide de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx) \(dans le [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]\).  
  
## Attributs OLE DB  
 Les [attributs du consommateur OLE DB](../../windows/ole-db-consumer-attributes.md) offrent un moyen commode pour créer des consommateurs OLE DB.  Les attributs OLE DB injectent un code basé sur les [modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) pour créer des consommateurs et des fournisseurs OLE DB de travail.  Si vous devez spécifier une fonctionnalité qui n'est pas prise en charge par les attributs, vous pouvez utiliser les modèles OLE DB en combinaison avec les attributs contenus dans votre code.  
  
## Classes OLE DB MFC  
 La bibliothèque MFC possède une classe, [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), qui affiche des enregistrements de base de données dans des contrôles.  La vue est une vue de type formulaire directement connectée à un objet `CRowset`, et affiche les champs de l'objet `CRowset` dans les contrôles du modèle de boîte de dialogue.  Elle fournit également une implémentation par défaut pour vous permettre de vous déplacer d'un enregistrement au suivant, au précédent, au premier ou au dernier, ainsi qu'une interface pour la mise à jour de l'enregistrement actuellement affiché.  Pour plus d'informations, consultez `COleDBRecordView`.  
  
## Interfaces du Kit de développement OLE DB SDK  
 Dans les cas où les modèles OLE DB ne prennent pas en charge la fonctionnalité OLE DB, vous devez utiliser les interfaces OLE DB elles\-mêmes.  Pour plus d'informations sur les curseurs, consultez le [Guide de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms713643.aspx) du [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
## Voir aussi  
 [Programmation OLE DB](../../data/oledb/ole-db-programming.md)   
 [Vue d'ensemble de la programmation OLE DB](../../data/oledb/ole-db-programming-overview.md)