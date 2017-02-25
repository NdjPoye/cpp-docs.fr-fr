---
title: "Comment&#160;: &#233;tablir la liaison des donn&#233;es DDX/DDV avec Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC (C++), héberger un contrôle Windows Forms"
  - "Windows Forms (C++), prise en charge des MFC"
ms.assetid: b2957370-cf1f-4779-94ac-228cd393686c
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Comment&#160;: &#233;tablir la liaison des donn&#233;es DDX/DDV avec Windows Forms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[DDX\_ManagedControl](../Topic/DDX_ManagedControl.md) appelle [CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md) pour créer un contrôle correspondant à l'ID du contrôle de ressource.  Si vous utilisez `DDX_ManagedControl` pour un contrôle `CWinFormsControl` \(dans le code généré par l'Assistant\), n'appelez pas `CreateManagedControl` explicitement pour le même contrôle.  
  
 Appelez `DDX_ManagedControl` dans [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md) pour créer des contrôles d'ID de ressource.  Pour l'échange de données, vous ne devez pas utiliser les fonctions DDX\/DDV avec les contrôles Windows Forms.  À la place, vous pouvez placer le code pour accéder aux propriétés du contrôle managé dans la méthode `DoDataExchange` de votre classe de dialogue \(ou vue\), comme dans l'exemple suivant.  
  
 L'exemple suivant montre comment lier une chaîne C\+\+ native à un contrôle utilisateur .NET.  
  
## Exemple  
 Les éléments suivants sont un exemple de liaison de données DDX\/DDV d'un `m_str` de chaîne MFC avec la propriété `NameText` définie par l'utilisateur d'un contrôle utilisateur .NET.  
  
 Le contrôle est créé lorsque [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md) appelle `CMyDlg::DoDataExchange` pour la première fois, afin que tout code qui référence `m_UserControl` se produise après l'appel `DDX_ManagedControl`.  
  
 Vous pouvez implémenter ce code dans l'application MFC01 que vous avez créée dans [Comment : créer le contrôle utilisateur et l'héberger dans une boîte de dialogue](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
 Insérez le code suivant dans la déclaration de CMFC01Dlg :  
  
```  
class CMFC01Dlg : public CDialog  
{  
   CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_MyControl;  
   CString m_str;  
};  
```  
  
## Exemple  
 Insérez le code suivant dans l'implémentation de CMFC01Dlg :  
  
```  
void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
{  
   CDialog::DoDataExchange(pDX);  
   DDX_ManagedControl(pDX, IDC_CTRL1, m_MyControl);  
  
   if (pDX->m_bSaveAndValidate) {  
      m_str = m_MyControl->textBox1->Text;  
   } else  
   {  
      m_MyControl->textBox1->Text = gcnew System::String(m_str);  
   }  
}  
```  
  
## Exemple  
 Nous allons maintenant ajouter la méthode de gestionnaire en cliquant sur le bouton OK.  Cliquez sur l'onglet **Affichage des ressources**.  Dans Affichage des ressources, double\-cliquez sur `IDD_MFC01_DIALOG`.  La ressource de boîte de dialogue apparaît dans l'Éditeur de ressources.  Double\-cliquez ensuite sur le bouton OK.  
  
 Définissez le gestionnaire comme suit.  
  
```  
void CMFC01Dlg::OnBnClickedOk()  
{  
   AfxMessageBox(CString(m_MyControl.GetControl()->textBox1->Text));  
   OnOK();  
}  
```  
  
## Exemple  
 Et ajoutez la ligne suivante à l'implémentation de BOOL CMFC01Dlg::OnInitDialog \(\).  
  
```  
m_MyControl.GetControl()->textBox1->Text = "hello";  
```  
  
 Vous pouvez maintenant générer et exécuter l'application.  Notez que le texte contenu dans la zone de texte s'affiche dans un message contextuel à la fermeture de l'application.  
  
## Voir aussi  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md)   
 [DDX\_ManagedControl](../Topic/DDX_ManagedControl.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)