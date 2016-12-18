---
title: "Contr&#244;les ActiveX MFC&#160;: impl&#233;mentation des propri&#233;t&#233;s avanc&#233;es | Microsoft Docs"
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
  - "contrôles ActiveX MFC, codes d'erreur"
  - "contrôles ActiveX MFC, propriétés"
  - "propriétés (MFC), contrôles ActiveX"
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: impl&#233;mentation des propri&#233;t&#233;s avanc&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les rubriques relatives à l'implémentation des propriétés avancées dans un contrôle ActiveX :  
  
-   [Propriétés en lecture seule et en écriture seule](#_core_read2donly_and_write2donly_properties)  
  
-   [Renvoi des codes d'erreur d'une propriété](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> Propriétés en lecture seule et en écriture seule  
 Type de données c offre une méthode rapide et facile pour implémenter les propriétés en lecture seule ou en écriture seule pour le contrôle.  
  
#### Pour implémenter une propriété en lecture seule ou en écriture seule  
  
1.  Chargez votre projet.  
  
2.  Sous Class View, développez l'arborescence de votre librairie.  
  
3.  Cliquez avec le bouton droit sur le nœud de votre interface \(le deuxième nœud de l'arborescence de la librairie\) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
     Cela ouvre l'[Assistant Ajout de Propriétés](../ide/names-add-property-wizard.md).  
  
5.  Dans la zone **Nom de la propriété**, tapez un nom pour votre nouvelle propriété.  
  
6.  Dans **Type d'implémentation**, cliquez sur **Méthodes Get\/Set**.  
  
7.  Dans la zone de **Type de propriété**, sélectionnez le type approprié pour la propriété.  
  
8.  Si vous souhaitez une propriété en lecture seule, désactivez le nom de fonction définie.  Si vous souhaitez une propriété en lecture seule, désactivez le nom de fonction définie.  
  
9. Cliquez sur **Terminer**.  
  
 Dans ce cas, type de données c insère la fonction `SetNotSupported` ou `GetNotSupported` dans l'entrée de dispatch à la place d'un jeu ou d'une fonction système standard.  
  
 Si vous souhaitez modifier une propriété existante comme étant en lecture seule ou en lecture seule, vous pouvez modifier la table de dispatch manuellement et supprimer tout ou la fonction Get inutile de la classe de contrôle.  
  
 Si vous souhaitez une propriété comme condition en lecture seule ou en lecture seule \(par exemple, lorsque votre contrôle s'exécute dans un mode spécifique\), vous pouvez fournir tout ou la fonction système, comme la normale, et appelez la fonction d'`SetNotSupported` ou d'`GetNotSupported` le cas échéant.  Par exemple :  
  
 [!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/CPP/mfc-activex-controls-advanced-property-implementation_1.cpp)]  
  
 Cet exemple de code appelle `SetNotSupported` si le membre de données de `m_bReadOnlyMode` est **TRUE**.  Si **FALSE**, la propriété est définie à la nouvelle valeur.  
  
##  <a name="_core_returning_error_codes_from_a_property"></a> Renvoi des codes d'erreur d'une propriété  
 Pour indiquer qu'une erreur s'est produite lors de la tentative d'obtenir ou définir une propriété, utilisez la fonction d'`COleControl::ThrowError`, qui prend `SCODE` \(code d'état\) en tant que paramètre.  Vous pouvez utiliser `SCODE` prédéfini ou définir un de vos propres.  Pour obtenir la liste des `SCODE`prédéfini s et instruction pour définir `SCODE`personnalisé s, consultez l'[Gestion des erreurs dans le contrôle ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) dans les contrôles ActiveX d'article : Rubriques avancées.  
  
 Les fonctions d'assistance existent pour la plupart des `SCODE`prédéfini par courantes s, tel qu' [COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md), [COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md), et [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md).  
  
> [!NOTE]
>  `ThrowError` est destiné à être utilisé uniquement comme méthode de retourner une erreur de la fonction de l'obtention ou de l'ensemble d'une propriété ou d'une méthode automation.  Ce sont les seuls temps que le gestionnaire des exceptions approprié est présent dans la pile.  
  
 Pour plus d'informations sur les exceptions de rapports dans d'autres zones de code, consultez [COleControl::FireError](../Topic/COleControl::FireError.md) et la section [Gestion des erreurs dans le contrôle ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) dans les contrôles ActiveX d'article : Rubriques avancées.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : propriétés](../mfc/mfc-activex-controls-properties.md)   
 [Contrôles ActiveX MFC : méthodes](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)