---
title: "Comment&#160;: recevoir des &#233;v&#233;nements Windows Forms de classes C++ natives | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des événements, interopérabilité native/.NET"
  - "gestion des événements, interopérabilité native/managée"
  - "gestion des événements, réception du .NET en C++"
  - "gestion des événements, Windows Forms en C++"
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: recevoir des &#233;v&#233;nements Windows Forms de classes C++ natives
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez permettre aux classes C\+\+ natives de recevoir des rappels d'événements managés déclenchés à partir de contrôles Windows Forms ou d'autres formulaires avec le format de mappage de macro MFC.  La réception des événements dans les vues et les dialogues est similaire à l'exécution de la même tâche pour les contrôles.  
  
 Pour cela, vous devez :  
  
-   Joignez un gestionnaire d'événements `OnClick` au contrôle à l'aide de [MAKE\_DELEGATE](../Topic/MAKE_DELEGATE.md).  
  
-   Créez un mappage de délégué à l'aide de [BEGIN\_DELEGATE\_MAP](../Topic/BEGIN_DELEGATE_MAP.md), [END\_DELEGATE\_MAP](../Topic/END_DELEGATE_MAP.md) et [EVENT\_DELEGATE\_ENTRY](../Topic/EVENT_DELEGATE_ENTRY.md).  
  
 Cet exemple continue les tâches que vous avez effectuées dans [Comment : établir la liaison des données DDX\/DDV avec Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).  
  
 Vous allez maintenant associer votre contrôle MFC \(`m_MyControl`\) à un délégué de gestionnaires d'événements managé appelé `OnClick` pour l'événement <xref:System.Windows.Forms.Control.Click> managé.  
  
### Pour attacher le gestionnaire d'événements OnClick :  
  
1.  Ajoutez le code suivant à l'implémentation de BOOL CMFC01Dlg::OnInitDialog :  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  Ajoutez le code suivant à la section publique figurant dans la déclaration de classe CMFC01Dlg : public CDialog.  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  Enfin, ajoutez l'implémentation pour `OnClick` à CMFC01Dlg.cpp :  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## Voir aussi  
 [MAKE\_DELEGATE](../Topic/MAKE_DELEGATE.md)   
 [BEGIN\_DELEGATE\_MAP](../Topic/BEGIN_DELEGATE_MAP.md)   
 [END\_DELEGATE\_MAP](../Topic/END_DELEGATE_MAP.md)   
 [EVENT\_DELEGATE\_ENTRY](../Topic/EVENT_DELEGATE_ENTRY.md)