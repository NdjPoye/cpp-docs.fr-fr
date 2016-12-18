---
title: "&#201;diteur de bo&#238;tes de dialogue, onglet de la bo&#238;te &#224; outils | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "Boîte à outils (C++), onglet Éditeur de boîtes de dialogue"
  - "contrôles (C++), types"
  - "contrôles syslink dans les boîtes de dialogue"
  - "contrôles personnalisés (Visual Studio), boîtes de dialogue"
  - "contrôles (C++), standard"
  - "Éditeur de boîtes de dialogue, création de contrôles"
  - "contrôles [C++], ajouter aux boîtes de dialogue"
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;diteur de bo&#238;tes de dialogue, onglet de la bo&#238;te &#224; outils
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L’onglet Éditeur de boîtes de dialogue s’affiche dans la fenêtre [Boîte à outils](../Topic/Toolbox.md) lorsque vous travaillez dans l’Éditeur de boîtes de dialogue. Pour ajouter des contrôles à votre nouvelle boîte de dialogue, faites\-les glisser de la boîte à outils vers la boîte de dialogue que vous créez \(pour plus d’informations, consultez [Ajout d’un contrôle dans une boîte de dialogue](../mfc/adding-a-control-to-a-dialog-box.md)\). Vous pouvez ensuite déplacer les contrôles ou modifier leur taille et leur forme.  
  
 Les contrôles standard disponibles dans la boîte à outils sont les suivants :  
  
-   [Contrôle Button](../mfc/reference/cbutton-class.md)  
  
-   [Contrôle Check Box](../mfc/reference/button-styles.md)  
  
-   [Contrôle Combo Box](../mfc/reference/ccombobox-class.md)  
  
-   [Contrôle Edit](../mfc/reference/cedit-class.md)  
  
-   Contrôle Group box  
  
-   [Contrôle List Box](../mfc/reference/clistbox-class.md)  
  
-   [Contrôle Radio Button](../mfc/reference/button-styles.md)  
  
-   [Contrôle Static Text](../mfc/reference/cstatic-class.md)  
  
-   [Contrôle Picture](../mfc/reference/cpictureholder-class.md)  
  
-   [Contrôle Rich Edit 2.0](../mfc/using-cricheditctrl.md)  
  
-   [Contrôle de barre de défilement](../mfc/reference/cscrollbar-class.md)  
  
 Les [Contrôles communs Windows](../mfc/controls-mfc.md) disponibles dans la boîte à outils fournissent des fonctionnalités améliorées dans votre application. Ils comprennent :  
  
-   [Contrôle Slider](../mfc/slider-control-styles.md)  
  
-   [Contrôle Spin](../mfc/using-cspinbuttonctrl.md)  
  
-   [Contrôle Progress](../mfc/styles-for-the-progress-control.md)  
  
-   [Contrôle Hot Key](../mfc/using-a-hot-key-control.md)  
  
-   [Contrôle List](../mfc/list-control-and-list-view.md)  
  
-   [Contrôle Tree](../mfc/tree-control-styles.md)  
  
-   [Contrôle Tab](../mfc/tab-controls-and-property-sheets.md)  
  
-   [Contrôle Animation](../mfc/using-an-animation-control.md)  
  
-   [Contrôle Date Time Picker](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [Contrôle Month Calendar](../mfc/month-calendar-control-examples.md)  
  
-   [Contrôle IP Address](../mfc/reference/cipaddressctrl-class.md)  
  
-   [Contrôle Extended Combo Box](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [Contrôle personnalisé](../mfc/custom-controls-in-the-dialog-editor.md)  
  
 Vous pouvez ajouter des contrôles personnalisés à la boîte de dialogue en sélectionnant l’icône **Contrôle personnalisé** dans la boîte à outils et en la faisant glisser vers votre boîte de dialogue. Pour ajouter un contrôle Syslink, ajoutez un contrôle personnalisé, puis attribuez la valeur **Syslink** à la propriété **Classe** du contrôle. Cela entraînera l’actualisation des propriétés et l’affichage des propriétés du contrôle Syslink. Pour plus d’informations sur la classe wrapper MFC, consultez [CLinkCtrl](../mfc/reference/clinkctrl-class.md).  
  
 Vous pouvez également [ajouter des contrôles ActiveX à votre boîte de dialogue](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Vous pouvez également personnaliser la fenêtre Boîte à outils pour faciliter son utilisation. Pour plus d’informations, consultez [Gestion des éléments et des onglets de la boîte à outils](http://msdn.microsoft.com/fr-fr/21285050-cadd-455a-b1f5-a2289a89c4db). Par exemple, vous pouvez placer des contrôles dans la fenêtre Boîte à outils pour en faciliter l’accès. Pour plus d’informations, consultez [Personnaliser la boîte de dialogue Boîte à outils](http://msdn.microsoft.com/fr-fr/bd07835f-18a8-433e-bccc-7141f65263bb).  
  
 Pour plus d’informations sur l’utilisation du contrôle RichEdit 1.0 avec MFC, consultez [Utilisation du contrôle RichEdit 1.0 avec MFC](../mfc/using-the-richedit-1-0-control-with-mfc.md).  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/fr-fr/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)   
 [Classes de contrôle](../mfc/control-classes.md)   
 [Classes de boîte de dialogue](../mfc/dialog-box-classes.md)   
 [Styles de barre de défilement](../mfc/reference/scroll-bar-styles.md)   
 [Exemples de contrôle RichEdit](../mfc/rich-edit-control-examples.md)   
 [Adding Event Handlers for Dialog Box Controls](../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [Contrôles de boîtes de dialogue et types de variables](../ide/dialog-box-controls-and-variable-types.md)