---
title: "H&#233;bergement d&#39;un contr&#244;le utilisateur Windows Form dans une bo&#238;te de dialogue MFC | Microsoft Docs"
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
  - "Windows Forms (C++), prise en charge des MFC"
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# H&#233;bergement d&#39;un contr&#244;le utilisateur Windows Form dans une bo&#238;te de dialogue MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC héberge un contrôle Windows Forms sous la forme d'un type spécial de contrôle ActiveX et communique avec le contrôle via des interfaces ActiveX ainsi que des propriétés et des méthodes de la classe <xref:System.Windows.Forms.Control>.  Nous vous recommandons d'utiliser des propriétés et des méthodes .NET Framework pour agir sur le contrôle.  
  
 Pour obtenir un exemple d'application qui illustre l'utilisation des Windows Forms avec MFC, consultez [Intégration MFC et Windows Forms \(page éventuellement en anglais\)](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
> [!NOTE]
>  Dans la version actuelle, un objet `CDialogBar`  ne peut pas héberger de contrôles Windows Forms.  
  
## Dans cette section  
 [Comment : créer le contrôle utilisateur et l'héberger dans une boîte de dialogue](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [Comment : établir la liaison des données DDX\/DDV avec Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [Comment : recevoir des événements Windows Forms de classes C\+\+ natives](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## Référence  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog Class](../mfc/reference/cdialog-class.md) &#124; [CWnd, classe](../mfc/reference/cwnd-class.md) &#124; <xref:System.Windows.Forms.Control>  
  
## Voir aussi  
 [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Différences de programmation entre Windows Forms et MFC](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Hébergement d'un contrôle utilisateur Windows Forms en tant que vue MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Hébergement d'un contrôle utilisateur Windows Form en tant que boîte de dialogue MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)