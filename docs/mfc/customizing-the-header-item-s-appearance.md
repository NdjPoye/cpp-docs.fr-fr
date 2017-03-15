---
title: "Personnalisation de l&#39;apparence de l&#39;&#233;l&#233;ment d&#39;en-t&#234;te | Microsoft Docs"
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
  - "CHeaderCtrl (classe), personnaliser les éléments"
  - "HDS_ (styles)"
  - "contrôles header, personnalisation des éléments"
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Personnalisation de l&#39;apparence de l&#39;&#233;l&#233;ment d&#39;en-t&#234;te
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En définissant le paramètre *dwStyle* lorsque vous créez un contrôle header \([CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md)\), vous pouvez définir l'apparence et le comportement des éléments d'en\-tête ou du contrôle header lui\-même.  
  
 Voici un échantillonnage des styles que vous pouvez définir, et leur objectif :  
  
-   Pour créer un exemple d'élément d'en\-tête dans un bouton poussoir, utilisez le style `HDS_BUTTONS`.  
  
     Utilisez ce style si vous souhaitez effectuer des actions en réponse à des clics de souris sur un élément d'en\-tête, tels que trier les données d'une colonne particulière, comme cela est fait dans Microsoft Outlook.  
  
-   Pour donner aux éléments d'en\-tête une apparence de « sélection réactive » lorsque le curseur de la souris passe sur elles, utilisez le style `HDS_HOTTRACK`.  
  
     La sélection réactive affiche un plan 3D tandis que le pointeur passe sur un élément dans une barre en deux dimensions.  
  
-   Pour indiquer que le contrôle header doit être masqué, utilisez le style `HDS_HIDDEN`.  
  
     Le style `HDS_HIDDEN` indique que le contrôle header est destiné à être utilisé comme conteneur de données et non comme contrôle visuel.  Ce style ne masque pas automatiquement le contrôle, mais à la place, affecte le comportement `CHeaderCtrl::Layout`.  La valeur retournée dans le membre **cy** de la structure `WINDOWPOS` est zéro, ce qui indique que le contrôle ne doit pas être accessible à l'utilisateur.  
  
 Pour plus d'informations sur ces propriétés, consultez [Items](http://msdn.microsoft.com/library/windows/desktop/bb775238) dans le [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  Pour plus d'informations sur l'ajout d'éléments à un contrôle header, consultez [Ajout d'éléments dans le contrôle header](../mfc/adding-items-to-the-header-control.md).  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)