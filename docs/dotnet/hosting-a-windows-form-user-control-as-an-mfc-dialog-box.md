---
title: "H&#233;bergement d&#39;un contr&#244;le utilisateur Windows Form en tant que bo&#238;te de dialogue MFC | Microsoft Docs"
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
  - "Windows Forms (C++), héberger en tant que boîte de dialogue MFC"
ms.assetid: 0434a9d7-8b14-48e6-ad69-9ba9a684677a
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# H&#233;bergement d&#39;un contr&#244;le utilisateur Windows Form en tant que bo&#238;te de dialogue MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC fournit le classe de modèle [CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md) pour vous permettre d'héberger un contrôle utilisateur Windows Forms \(<xref:System.Windows.Forms.UserControl>\) dans une boîte de dialogue MFC modale ou non modale.  `CWinFormsDialog` est dérivé de la classe MFC [CDialog](../mfc/reference/cdialog-class.md), donc la boîte de dialogue peut être lancée en tant que modale ou non modale.  
  
 Le processus que `CWinFormsDialog` utilise pour héberger le contrôle utilisateur est similaire à celui qui est décrit dans [Hébergement d'un contrôle utilisateur Windows Form dans une boîte de dialogue MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md).  Toutefois, `CWinFormsDialog` gère l'initialisation et l'hébergement du contrôle utilisateur afin qu'il ne soit pas nécessaire de le programmer manuellement.  
  
 Pour obtenir un exemple d'application qui illustre l'utilisation des Windows Forms avec MFC, consultez [Intégration MFC et Windows Forms \(page éventuellement en anglais\)](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
### Pour créer l'application MFC hôte  
  
1.  Créez un projet d'application MFC.  
  
     Dans le menu **Fichier**, sélectionnez **Nouveau**, puis cliquez sur **Projet**.  Dans le dossier **Visual C\+\+**, sélectionnez **Application MFC**.  
  
     Dans la zone **Nom**, entrez `MFC03` et modifiez le paramètre Solution en **Ajouter à la solution**.Cliquez sur **OK**.  
  
     Dans l'**Assistant Application MFC**, acceptez toutes les valeurs par défaut, puis cliquez sur **Terminer**.  Cela crée une application MFC avec une interface multidocument.  
  
2.  Configurez le projet.  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud du projet **MFC03** et sélectionnez **Propriétés**.  La boîte de dialogue **Pages de propriétés** s'affiche.  
  
     Dans la boîte de dialogue **Pages de propriétés**, dans le contrôle d'arborescence **Propriétés de configuration**, sélectionnez **Général** puis, dans la section **Paramètres par défaut du projet**, affectez à **Prise en charge du Common Language Runtime**  la valeur **Common Language Runtime Support \(\/clr\)**.  Cliquez sur **OK**.  
  
3.  Ajoutez une référence au contrôle .NET.  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud du projet **MFC03** et choisissez **Ajouter**, **Références**.  Dans **Pages de propriétés**, cliquez sur **Ajouter une nouvelle référence**, sélectionnez WindowsControlLibrary1 \(sous l'onglet **Projets**\) et cliquez sur **OK**.  Cela ajoute une référence sous la forme d'une option du compilateur [\/FU](../build/reference/fu-name-forced-hash-using-file.md) afin que le programme exécute la compilation ; cela copie également WindowsControlLibrary1.dll dans le répertoire du projet `MFC03` afin que le programme s'exécute.  
  
4.  Ajoutez `#include <afxwinforms.h>` à stdafx.h, à la fin des instructions `#include` existantes.  
  
5.  Ajoutez une nouvelle classe qui sous\-classe `CDialog`.  
  
     Cliquez avec le bouton droit sur le nom du projet et ajoutez une classe MFC \(appelée CHostForWinForm\) qui sous\-classe `CDialog`.  La ressource de la boîte de dialogue n'étant pas nécessaire, vous pouvez supprimer l'ID de la ressource \(sélectionnez Affichage des ressources, développez le dossier Boîte de dialogue et supprimez la ressource IDD\_HOSTFORWINFORM.  Supprimez ensuite les références à l'ID dans le code\).  
  
6.  Remplacez `CDialog` dans les fichiers CHostForWinForm.h et CHostForWinForm.cpp par `CWinFormsDialog<WindowsControlLibrary1::UserControl1>`.  
  
7.  Appelez DoModal sur la classe CHostForWinForm.  
  
     Dans MFC03.cpp, ajoutez `#include "HostForWinForm.h"`.  
  
     Avant l'instruction return dans la définition de CMFC03App::InitInstance, ajoutez :  
  
     `CHostForWinForm m_HostForWinForm;`  
  
     `m_HostForWinForm.DoModal();`  
  
8.  Générez et exécutez le projet.  
  
     Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
     Dans le menu **Déboguer**, cliquez sur **Exécuter sans débogage**.  
  
     Ajoutez ensuite le code pour contrôler l'état d'un contrôle sur les Windows Forms de l'application MFC.  
  
9. Ajoutez un gestionnaire pour OnInitDialog.  
  
     Affichez la fenêtre **Propriétés** \(F4\).  Dans **Affichage de classes**, sélectionnez CHostForWinForm.  Dans la fenêtre **Propriétés**, sélectionnez des substitutions, cliquez dans la colonne de gauche de la ligne correspondant à OnInitDialog, puis sélectionnez \< Ajouter \>.  La ligne suivante est ajoutée à CHostForWinForm.h :  
  
    ```  
    virtual BOOL OnInitDialog();  
    ```  
  
10. Définissez OnInitDialog \(dans CHostForWinForm.cpp\) comme suit :  
  
    ```  
    BOOL CHostForWinForm::OnInitDialog() {  
       CWinFormsDialog<WindowsControlLibrary1::UserControl1>::OnInitDialog();  
       GetControl()->button1->Click += MAKE_DELEGATE(System::EventHandler, OnButton1);  
       return TRUE;  
    }  
    ```  
  
11. Ajoutez ensuite le gestionnaire OnButton1.  Ajoutez les lignes suivantes à la section publique de la classe CHostForWinForm contenue dans CHostForWinForm.h :  
  
    ```  
    virtual void OnButton1( System::Object^ sender, System::EventArgs^ e );  
  
    BEGIN_DELEGATE_MAP( CHostForWinForm )  
       EVENT_DELEGATE_ENTRY( OnButton1, System::Object^, System::EventArgs^ );  
    END_DELEGATE_MAP()  
    ```  
  
     Dans CHostForWinForm.cpp, ajoutez la définition suivante :  
  
    ```  
    void CHostForWinForm::OnButton1( System::Object^ sender, System::EventArgs^ e )   
    {  
       System::Windows::Forms::MessageBox::Show("test");  
    }  
    ```  
  
12. Générez et exécutez le projet.  Lorsque vous cliquez sur le bouton présent sur le Windows Form, le code de l'application MFC s'exécute.  
  
     Ajoutez ensuite le code pour afficher la valeur de la zone de texte sur le Windows Form à partir du code MFC.  
  
13. Dans la section publique de la classe CHostForWinForm contenue dans CHostForWinForm.h, ajoutez la déclaration suivante :  
  
    ```  
    CString m_sEditBoxOnWinForm;  
    ```  
  
14. Dans la définition de DoDataExchange dans CHostForWinForm.cpp, ajoutez les trois lignes suivantes à la fin de la fonction :  
  
    ```  
    if (pDX->m_bSaveAndValidate)  
       m_sEditBoxOnWinForm = CString( GetControl()->textBox1->Text);  
    else  
       GetControl()->textBox1->Text = gcnew System::String(m_sEditBoxOnWinForm);  
    ```  
  
15. Dans la définition de OnButton dans CHostForWinForm.cpp, ajoutez les trois lignes suivantes à la fin de la fonction :  
  
    ```  
    this->UpdateData(TRUE);  
    System::String ^ z = gcnew System::String(m_sEditBoxOnWinForm);  
    System::Windows::Forms::MessageBox::Show(z);  
    ```  
  
16. Générez et exécutez le projet.  
  
## Voir aussi  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)