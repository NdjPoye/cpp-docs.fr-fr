---
title: "Adding Controls to a Dialog Causes the Dialog to No Longer Function | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "controls [C++], troubleshooting"
  - "common controls, troubleshooting"
  - "troubleshooting controls"
  - "dialog boxes, troubleshooting"
  - "dialog box controls, troubleshooting"
  - "InitCommonControls"
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Controls to a Dialog Causes the Dialog to No Longer Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Après avoir ajouté un contrôle commun ou un contrôle RichEdit dans une boîte de dialogue, il n'apparaît pas lorsque vous testez la boîte de dialogue, ou la boîte de dialogue n'apparaît pas.  
  
 **Exemple du problème**  
  
1.  Créez un projet Win32, en modifiant les paramètres de l'application afin de pouvoir créer une application Windows \(et non une application console\).  
  
2.  Dans l'[Affichage des ressources](../windows/resource-view-window.md), double\-cliquez sur le fichier .rc.  
  
3.  Sous les options de la boîte de dialogue, double\-cliquez sur la zone **À propos de**.  
  
4.  Ajoutez un **contrôle IP Address** à la boîte de dialogue.  
  
5.  Enregistrez et cliquez sur **Régénérer tout**.  
  
6.  Exécutez le programme.  
  
7.  Dans le menu **?** \(Aide\) de la boîte de dialogue, cliquez sur la commande **À propos de** ; aucune boîte de dialogue ne s'affiche.  
  
 **La cause**  
  
 Actuellement, l'Éditeur de boîtes de dialogue n'ajoute pas automatiquement le code à votre projet lorsque vous faites glisser les contrôles communs ou RichEdit dans une boîte de dialogue.  De même, Visual Studio n'affiche pas une erreur ou un avertissement lorsque le problème se pose.  Vous devez ajouter le code pour les contrôles manuellement.  
  
||||  
|-|-|-|  
|Contrôle Slider|Contrôle Tree|Date Time Picker|  
|Contrôle Spin|Contrôle Tab|Month calendar|  
|Contrôle Progress|Contrôle Animation|Contrôle IP Address|  
|Hot Key|Contrôle RichEdit|Extended Combo Box|  
|Contrôle List|Contrôle RichEdit 2.0|Contrôle personnalisé|  
  
## Pour corriger pour les contrôles communs  
 Afin d'utiliser les contrôles communs dans une boîte de dialogue, vous devez appeler [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) ou **AFXInitCommonControls** avant de créer la boîte de dialogue.  
  
## Pour corriger pour les contrôles RichEdit  
 Vous devez appeler **LoadLibrary** pour les contrôles RichEdit.  Pour plus d'informations, consultez [Utilisation du contrôle RichEdit 1.0 avec MFC](../mfc/using-the-richedit-1-0-control-with-mfc.md), [À propos des contrôles RichEdit](http://msdn.microsoft.com/library/windows/desktop/bb787873) dans le [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] et [Vue d'ensemble du contrôle RichEdit](../mfc/overview-of-the-rich-edit-control.md).  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Troubleshooting the Dialog Editor](../mfc/troubleshooting-the-dialog-editor.md)   
 [Dialog Editor](../mfc/dialog-editor.md)