---
title: "Item cannot be added to the Toolbox. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VB_E_NOTSUPPORTEDDATA"
  - "vs.message.0x800A0065"
ms.assetid: 69fa5e73-bbc6-462c-95ca-bf2ee32d43ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Item cannot be added to the Toolbox.
Cette erreur se produit généralement lorsque vous tentez d'ajouter un élément pour lequel la Boîte à outils ne peut pas afficher d'icône de raccourci.  
  
 Les éléments que la Boîte à outils peut afficher incluent :  
  
-   les contrôles et les composants .NET Framework installés sur votre ordinateur local.  
  
 **Remarque** Les contrôles et composants pour les formulaires Web [!INCLUDE[vstecasp](../misc/includes/vstecasp_md.md)] doivent avoir une propriété [AspNetHostingPermission.Level](https://msdn.microsoft.com/en-us/library/system.web.aspnethostingpermission.level.aspx) ayant la valeur « Illimité » pour être affiché dans la boîte à outils.  
  
-   Texte sélectionné qui a été déplacé ou collé à partir d'un éditeur Visual Studio, comme les extraits de code.  
  
 Les éléments que la Boîte à outils ne peut pas afficher incluent :  
  
-   Fichiers de classeur Excel.  
  
-   Assemblys .NET Framework installés sur les serveurs réseau partagés.  
  
    > [!NOTE]
    >  Comme un assembly ajouté à partir d'un chemin UNC n'est pas d'un niveau de confiance suffisant, les autorisations suffisantes pour être affiché dans la Boîte à outils ne lui sont pas accordées.  
  
### Pour corriger cette erreur  
  
1.  Utilisez la boîte de dialogue **Personnaliser la boîte à outils** pour ajouter un contrôle ou un composant installé sur votre ordinateur local à l'onglet actif de la Boîte à outils.  
  
     \- ou \-  
  
2.  Faites glisser ou collez le texte sélectionné à partir d'un éditeur Visual Studio vers la Boîte à outils.  
  
## Voir aussi  
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/fr-fr/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [How to: Manipulate Toolbox Tabs](http://msdn.microsoft.com/fr-fr/21285050-cadd-455a-b1f5-a2289a89c4db)   
 [boîte à outils](../Topic/Toolbox.md)