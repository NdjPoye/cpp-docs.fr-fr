---
title: "H&#233;bergement d&#39;un contr&#244;le utilisateur Windows Forms en tant que vue&#160;MFC | Microsoft Docs"
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
  - "héberger un contrôle Windows Forms (C++)"
  - "MFC (C++), prise en charge Windows Forms"
  - "contrôles Windows Forms (C++), héberger en tant que vue MFC"
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# H&#233;bergement d&#39;un contr&#244;le utilisateur Windows Forms en tant que vue&#160;MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC utilise la classe CWinFormsView pour héberger un contrôle utilisateur Windows Forms dans une vue MFC.  Les vues Windows Forms de MFC sont des contrôles ActiveX.  Le contrôle utilisateur est hébergé en tant qu'enfant de la vue native et occupe la zone cliente entière de la vue native.  
  
 Le résultat final est semblable au modèle utilisé par la [CFormView Class](../mfc/reference/cformview-class.md).  Vous pouvez ainsi profiter du runtime et du concepteur Windows Forms pour créer des vues basées sur des formulaires riches.  
  
 Dans la mesure où les vues Windows Forms de MFC sont des contrôles ActiveX, elles n'ont pas les mêmes `hwnd` que les vues MFC.  Elles ne peuvent pas non plus être passées en tant que pointeur vers une vue [CView](../mfc/reference/cview-class.md).  En général, utilisez des méthodes .NET Framework pour travailler avec des vues Windows Forms et dépendre moins de Win32.  
  
 Pour obtenir un exemple d'application qui illustre l'utilisation des Windows Forms avec MFC, consultez [Intégration MFC et Windows Forms \(page éventuellement en anglais\)](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
## Dans cette section  
 [Comment : créer le contrôle utilisateur et héberger l'affichage MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [Comment : ajouter le routage des commandes au contrôle Windows Forms](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [Comment : appeler des propriétés et des méthodes du contrôle Windows Forms](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## Voir aussi  
 [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Comment : créer des contrôles composites](../Topic/How%20to:%20Author%20Composite%20Controls.md)