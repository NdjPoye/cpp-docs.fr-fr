---
title: "CPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPtrList class"
  - "generic lists"
  - "listes, generic"
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge des listes de pointeurs void.  
  
## Syntaxe  
  
```  
class CPtrList : public CObject  
```  
  
## Membres  
 Les fonctions membres de `CPtrList` sont semblables aux fonctions membres de la classe [CObList](../../mfc/reference/coblist-class.md).  En raison de cette ressemblance, vous pouvez utiliser la documentation de référence de `CObList` pour les détails de fonction membre.  Partout où vous consultez un pointeur d'un `CObject` comme paramètre de fonction ou valeur de retour, substituez un pointeur vers `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 par exemple, traduit en  
  
 `void*& CPtrList::GetHead() const;`  
  
## Notes  
 `CPtrList` incorpore la macro de `IMPLEMENT_DYNAMIC` pour prendre en charge l'accès de type d'exécution et faire un dump à un objet `CDumpContext`.  Si vous avez besoin d'un dump d'éléments de liste individuel de pointeur, vous devez définir l'intensité de contexte de dump à 1 ou supérieur.  
  
 Les listes de pointeur ne peuvent pas être sérialisées.  
  
 Lorsqu'un objet `CPtrList` est supprimé, ou lorsque ses éléments sont supprimés, seuls les pointeurs sont supprimés, pas les entités qu'ils référencent.  
  
 Pour plus d'informations sur l'utilisation de `CPtrList`, consultez l'article[](../../mfc/collections.md "Collections").  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## Configuration requise  
 **En\-tête:** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CObList Class](../../mfc/reference/coblist-class.md)