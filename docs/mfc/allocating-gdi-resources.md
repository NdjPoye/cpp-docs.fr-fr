---
title: "Allocation de ressources GDI | Microsoft Docs"
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
  - "objets GDI, allouer pendant l'impression"
  - "imprimer (MFC), allouer des ressources GDI"
  - "ressources (MFC), imprimer"
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Allocation de ressources GDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment allouer et libérer les objets GDI \(Graphics Device Interface\) Windows pour l'impression.  
  
> [!NOTE]
>  GDI\+ est fourni avec Windows XP et est disponible sous forme de composant redistribuable pour Windows NT 4.0 SP6, Windows 2000, Windows 98 et Windows Me.  Pour télécharger le composant redistribuable le plus récent, consultez [http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm).  Pour plus d'informations, consultez la documentation du Kit de développement logiciel \(SDK\) GDI\+ dans MSDN : [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp).  
  
 Supposons que vous avez besoin d'utiliser des polices, des stylets ou d'autres objets GDI pour l'impression, mais pas pour l'affichage à l'écran.  Compte tenu de la mémoire qu'ils demandent, il n'est pas judicieux d'allouer ces objets au démarrage de l'application.  Quand l'application n'imprime pas un document, cette mémoire peut être utile à d'autres tâches.  Il est préférable de les allouer au début de l'impression, puis de les supprimer à la fin.  
  
 Pour allouer ces objets GDI, substituez la fonction membre [OnBeginPrinting](../Topic/CView::OnBeginPrinting.md).  Cette fonction est parfaitement adaptée à cette démarche pour deux raisons : l'infrastructure appelle cette fonction une fois au début de chaque travail d'impression et, contrairement à [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md), cette fonction a accès à l'objet [CDC](../mfc/reference/cdc-class.md) représentant le pilote du périphérique d'impression.  Vous pouvez stocker ces objets en vue de les utiliser pendant le travail d'impression en définissant des variables membres dans votre classe d'affichage qui pointent vers des objets GDI \(par exemple, les membres **CFont \***, et ainsi de suite\).  
  
 Pour utiliser les objets GDI que vous avez créés, sélectionnez\-les dans le contexte du périphérique d'impression dans la fonction membre [OnPrint](../Topic/CView::OnPrint.md).  Si vous avez besoin d'autres objets GDI pour les différentes pages du document, vous pouvez examiner le membre `m_nCurPage` de la structure [CPrintInfo](../mfc/reference/cprintinfo-structure.md) et sélectionner l'objet GDI en conséquence.  Si vous avez besoin d'un objet GDI pour plusieurs pages consécutives, Windows vous impose de le sélectionner dans le contexte du périphérique à chaque appel de `OnPrint`.  
  
 Pour libérer ces objets GDI, substituez la fonction membre [OnEndPrinting](../Topic/CView::OnEndPrinting.md).  L'infrastructure appelle cette fonction à la fin de chaque travail d'impression, ce qui vous donne la possibilité de libérer les objets GDI propres à l'impression avant que l'application revienne à d'autres tâches.  
  
## Voir aussi  
 [Impression](../mfc/printing.md)   
 [Impression par défaut](../mfc/how-default-printing-is-done.md)