---
title: "Mise en forme des caract&#232;res dans les contr&#244;les RichEdit | Microsoft Docs"
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
  - "CRichEditCtrl (classe), formatage de caractères dans"
  - "mise en forme (C++), caractères"
  - "contrôles RichEdit, formatage de caractères dans"
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mise en forme des caract&#232;res dans les contr&#244;les RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser les fonctions membres du contrôle RichEdit \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) pour mettre en forme les caractères et récupérer les informations de mise en forme.  Pour les caractères, vous pouvez spécifier la police, la taille, la couleur, et les effets comme gras, en italique, et protégé.  
  
 Vous pouvez appliquer une mise en forme de caractères à l'aide de les fonctions membres de [SetSelectionCharFormat](../Topic/CRichEditCtrl::SetSelectionCharFormat.md) et de [SetWordCharFormat](../Topic/CRichEditCtrl::SetWordCharFormat.md).  Pour déterminer la mise en forme de caractères actuelle du texte sélectionné, utilisez la fonction membre [GetSelectionCharFormat](../Topic/CRichEditCtrl::GetSelectionCharFormat.md).  La structure de [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) est utilisée avec ces fonctions de membre pour spécifier des attributs de caractères.  L'un des membres importants de **CHARFORMAT** est **dwMask**.  Dans `SetSelectionCharFormat` et `SetWordCharFormat`, **dwMask** spécifie quels attributs de caractère est défini par cet appel de fonction.  `GetSelectionCharFormat` indique les attributs du premier caractère de la sélection ; **dwMask** spécifie les attributs qui sont cohérents dans toute la sélection.  
  
 Vous pouvez également obtenir et définir « la mise en forme de caractères par défaut, » qui est la mise en forme appliquée à tous les caractères ensuite inséré.  Par exemple, si une application définit la mise en forme de caractères par défaut en gras et que l'utilisateur entre ensuite un caractère, le caractère sera en gras.  Pour obtenir et définir la mise en forme de caractères par défaut, utilisez les fonctions membres [GetDefaultCharFormat](../Topic/CRichEditCtrl::GetDefaultCharFormat.md) et [SetDefaultCharFormat](../Topic/CRichEditCtrl::SetDefaultCharFormat.md).  
  
 L'attribut « Protégé » d'un caractère ne modifie pas la présentation du texte.  Si l'utilisateur tente de modifier le texte protégé, un contrôle RichEdit envoie à la fenêtre parente un message de notification **EN\_PROTECTED**, ce qui permet à la fenêtre parente d'autoriser ou empêcher la modification.  Pour recevoir le message de notification, vous devez l'activer en utilisant la fonction membre [SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md).  Pour plus d'informations sur le filtre d'événement, consultez [Notifications d'un contrôle RichEdit](../mfc/notifications-from-a-rich-edit-control.md), plus loin dans cette rubrique.  
  
 La couleur de premier plan est un attribut de type caractère, mais la couleur d'arrière\-plan est une propriété du contrôle RichEdit.  Pour définir la couleur d'arrière\-plan, utilisez la fonction membre [SetBackgroundColor](../Topic/CRichEditCtrl::SetBackgroundColor.md).  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)