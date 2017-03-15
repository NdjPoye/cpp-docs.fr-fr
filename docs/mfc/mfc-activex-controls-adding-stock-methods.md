---
title: "Contr&#244;les ActiveX MFC&#160;: ajout de m&#233;thodes stock | Microsoft Docs"
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
  - "DoClick (méthode)"
  - "contrôles ActiveX MFC, méthodes"
  - "contrôles ActiveX MFC, méthodes stock"
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: ajout de m&#233;thodes stock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une méthode stock diffère d'une méthode personnalisée en ce qu'elle est déjà implémentée par la classe [COleControl](../mfc/reference/colecontrol-class.md).  Par exemple, `COleControl` contient une fonction membre prédéfinie qui prend en charge la méthode d'actualisation pour le contrôle.  L'entrée de dispatch pour cette méthode stock est **DISP\_STOCKFUNC\_REFRESH**.  
  
 '`COleControl` prend en charge deux méthodes stock : DoClick et l'actualisation.  L'actualisation est appelée par l'utilisateur du contrôle pour mettre à jour immédiatement l'apparence du contrôle ; DoClick est appelé pour déclencher l'événement Click du contrôle.  
  
|Méthode|Entrée de dispatch|Commentaire|  
|-------------|------------------------|-----------------|  
|`DoClick`|**DISP\_STOCKPROP\_DOCLICK\( \)**|Déclenche un événement Click.|  
|**Actualiser**|**DISP\_STOCKPROP\_REFRESH\( \)**|Met à jour immédiatement l'apparence du contrôle.|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a> Ajouter une méthode magasin à l'aide de l'assistant Ajout de méthode  
 Ajouter une méthode stock est simple en utilisant l'[Assistant Ajout de méthode](../ide/add-method-wizard.md).  La procédure suivante montre comment ajouter la méthode d'actualisation à un contrôle créé à l'aide de l'Assistant Contrôle ActiveX de MFC.  
  
#### Pour ajouter la méthode stock Actualiser en utilisant l'Assistant Ajout de Méthode  
  
1.  Chargez votre projet de contrôle.  
  
2.  Sous Class View, développez l'arborescence de votre librairie.  
  
3.  Cliquez avec le bouton droit sur le nœud de votre interface \(le deuxième nœud de l'arborescence de la librairie\) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une Méthode**.  
  
     Cela ouvre l'Assistant Ajout de la méthode.  
  
5.  Dans la zone de **Nom de méthode**, cliquez sur **Actualiser**.  
  
6.  Cliquez sur **Terminer**.  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a> Modifications de l'Assistant Ajout de la méthode pour les méthodes de stock  
 Comme la méthode de stock Actualiser est prise en charge par la classe de base du contrôle, l'**Assistant Ajout de méthode** ne modifie pas la déclaration de classe du contrôle de quelque manière que ce soit.  Elle ajoute une entrée pour la méthode à la table de dispatch du contrôle et à son fichier .IDL.  La ligne suivante est ajoutée à la table de dispatch de contrôle, située dans le fichier d'implémentation \(.CPP\) :  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 Cela rend la méthode Actualiser disponible aux utilisateurs du contrôle.  
  
 La ligne suivante est ajoutée au fichier .IDL :  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 Cette ligne affecte à la méthode d'actualiser un ID spécifique.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)