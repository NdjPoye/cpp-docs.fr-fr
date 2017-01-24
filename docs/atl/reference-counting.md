---
title: "Reference Counting | Microsoft Docs"
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
  - "AddRef method [C++]"
  - "AddRef method [C++], reference counting"
  - "reference counting"
  - "reference counts"
  - "références, compter"
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Reference Counting
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM n'essaie pas automatiquement de supprimer un objet de la mémoire lorsqu'il pense que l'objet n'est plus utilisé.  À la place, le programmeur d'objet doit supprimer l'objet non utilisé.  Le programmeur détermine si un objet peut être supprimé en fonction d'un nombre de références.  
  
 COM utilise les méthodes d' **IUnknown** , [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317), pour gérer le décompte de références d'interfaces sur un objet.  Les règles générales pour appeler ces méthodes sont :  
  
-   Chaque fois qu'un client reçoit un pointeur d'interface, `AddRef` doit être invité l'interface.  
  
-   Chaque fois que le client a terminé d'utiliser le pointeur d'interface, il doit appeler **Release**.  
  
 Dans une implémentation simple, les index de chaque appel d' `AddRef` et chaque appel de **Release** décrémente une variable compteur à l'intérieur de l'objet.  Lorsque retourne à zéro de nombre, l'interface n'a plus aucun utilisateur et est libre pour le supprimer de la mémoire.  
  
 Le décompte de références peut également être implémenté afin que chaque référence à l'objet \(pas à une interface individuelle\) soit numérotée.  Dans ce cas, les délégués chaque `AddRef` et appel de **Release** à une implémentation centrale sur l'objet, et **Release** libère l'objet entier lorsque ses atteint zéro de décompte de références.  
  
> [!NOTE]
>  Lorsque `CComObject`\- l'objet dérivé est construit à l'aide de l'opérateur **nouveau** , le décompte de références est 0.  Par conséquent, un appel à `AddRef` doit être effectuée après avoir créé avec succès `CComObject`objet dérivé.  
  
## Voir aussi  
 [Introduction to COM](../atl/introduction-to-com.md)   
 [Managing Object Lifetimes through Reference Counting](http://msdn.microsoft.com/library/windows/desktop/ms687260)