---
title: "Comment&#160;: appeler des propri&#233;t&#233;s et des m&#233;thodes du contr&#244;le Windows Forms | Microsoft Docs"
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
  - "appeler des méthodes, contrôle Windows Forms"
  - "appeler des propriétés"
  - "appeler des propriétés, contrôle Windows Forms"
  - "appels de méthode, Windows Forms"
  - "contrôles Windows Forms (C++), méthodes"
  - "contrôles Windows Forms (C++), propriétés"
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: appeler des propri&#233;t&#233;s et des m&#233;thodes du contr&#244;le Windows Forms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la mesure où [CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md) retourne un pointeur vers <xref:System.Windows.Forms.Control?displayProperty=fullName>, et non un pointeur vers `WindowsControlLibrary1::UserControl1`, il est recommandé d'ajouter un membre du type de contrôle utilisateur et de l'initialiser dans [IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md).  Vous pouvez maintenant appeler des méthodes et des propriétés à l'aide de `m_ViewControl`.  
  
 Cette rubrique part du principe que vous avez précédemment effectué les étapes [Comment : créer le contrôle utilisateur et l'héberger dans une boîte de dialogue](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) et [Comment : créer le contrôle utilisateur et héberger l'affichage MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### Pour créer l'application MFC hôte  
  
1.  Ouvrez l'application MFC que vous avez créée dans [Comment : créer le contrôle utilisateur et héberger l'affichage MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
2.  Ajoutez la ligne suivante à la section des substitutions publique de la déclaration de classe `CMFC02View` dans MFC02View.h.  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  Ajoutez une substitution pour OnInitialupdate.  
  
     Affichez la fenêtre **Propriétés** \(F4\).  Dans **Affichage de classes** \(CTRL\+MAJ\+C\), sélectionnez la classe CMFC02View.  Dans la fenêtre **Propriétés**, sélectionnez l'icône associée à Substitutions.  Faites défiler la liste vers le bas jusqu'à OnInitialUpdate.  Cliquez sur la liste déroulante et sélectionnez \<Ajouter\>.  assurez\-vous que le corps de la fonction OnInitialUpdate se présente comme suit :  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  Générez et exécutez le projet.  
  
     Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
     Dans le menu **Déboguer**, cliquez sur **Exécuter sans débogage**.  
  
     Notez que la zone de texte est maintenant initialisée.  
  
## Voir aussi  
 [Hébergement d'un contrôle utilisateur Windows Forms en tant que vue MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)