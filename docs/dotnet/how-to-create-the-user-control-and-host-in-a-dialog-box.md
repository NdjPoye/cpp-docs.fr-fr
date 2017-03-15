---
title: "Comment&#160;: cr&#233;er le contr&#244;le utilisateur et l&#39;h&#233;berger dans une bo&#238;te de dialogue | Microsoft Docs"
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
ms.assetid: 03a53032-2f03-4fa2-b567-031615a26011
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# Comment&#160;: cr&#233;er le contr&#244;le utilisateur et l&#39;h&#233;berger dans une bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les étapes de cet article supposent que vous créiez un projet MFC \(Microsoft Foundation Classes\) basé sur des boîtes de dialogue \([CDialog Class](../mfc/reference/cdialog-class.md)\) mais vous pouvez également ajouter la prise en charge d'un contrôle Windows Forms à une boîte de dialogue MFC existante.  
  
### Pour créer le contrôle utilisateur .NET  
  
1.  Créez un projet de bibliothèque de contrôles Windows Forms Visual C\# nommé `WindowsFormsControlLibrary1`.  
  
     Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet**.  Dans le dossier **Visual C\#** , sélectionnez **Bibliothèque de contrôles Windows Forms**.  
  
     Acceptez le nom de projet `WindowsFormsControlLibrary1` en cliquant **sur OK**.  
  
     Par défaut, le nom du contrôle .NET sera `UserControl1`.  
  
2.  Ajoutez les contrôles enfants à `UserControl1`.  
  
     Dans la **Boîte à outils**, ouvrez la liste **Tous les Windows Forms**.  Faites glisser un contrôle **Button** vers l'aire de conception `UserControl1`.  
  
     Ajoutez également un contrôle **TextBox**.  
  
3.  Dans l'**Explorateur de solutions**, double\-cliquez sur **UserControl1.Designer.cs** afin de l'ouvrir pour le modifier.  Modifiez les déclarations de la zone de texte et du bouton de `private` en `public`.  
  
4.  Générez le projet.  
  
     Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
### Pour créer l'application MFC hôte  
  
1.  Créez un projet d'application MFC.  
  
     Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet**.  Dans le dossier **Visual C\+\+**, sélectionnez **Application MFC**.  
  
     Dans la zone **Nom**, tapez `MFC01`.  Modifiez le paramètre Solution en **Ajouter à la solution**.  Cliquez sur **OK**.  
  
     Dans l'**Assistant Application MFC**, pour Type d'application, sélectionnez **Basée sur des boîtes de dialogue**.  Acceptez les paramètres par défaut restants, puis cliquez sur **Terminer**.  Cette opération crée une application MFC comportant une boîte de dialogue MFC.  
  
2.  Ajoutez un contrôle d'espace réservé à la boîte de dialogue MFC.  
  
     Dans le menu **Affichage**, cliquez sur **Affichage des ressources**.  Dans **Affichage des ressources**, développez le dossier **Boîte de dialogue**, puis double\-cliquez sur `IDD_MFC01_DIALOG`.  La ressource de boîte de dialogue apparaît dans l'**Éditeur de ressources**.  
  
     Dans la **Boîte à outils**, ouvrez la liste **Éditeur de boîtes de dialogue**.  Faites glisser un contrôle **Texte statique** vers la ressource de boîte de dialogue.  Le contrôle **Texte statique** servira d'espace réservé pour le contrôle Windows Forms .NET.  Redimensionnez\-le à environ la taille du contrôle Windows Forms.  
  
     Dans la fenêtre **Propriétés**, modifiez l'**ID** du contrôle **Texte statique** en `IDC_CTRL1` et modifiez la propriété **TabStop** en **True**.  
  
3.  Configurez le projet pour la prise en charge du Common Language Runtime \(CLR\).  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud de projet MFC01, puis cliquez sur **Propriétés**.  
  
     Dans la boîte de dialogue **Pages de propriétés**, sous **Propriétés de configuration**, sélectionnez **Général**.  Dans la section **Paramètres par défaut du projet**, attribuez à **Prise en charge du Common Language Runtime** la valeur **Prise en charge du Common Language Runtime \(\/clr\)**.  
  
     Sous **Propriétés de configuration**, développez **C\/C\+\+**, puis sélectionnez le nœud **Général**.  Affectez à **Format des informations de débogage** la valeur **Base de données du programme \(\/Zi\)**.  
  
     Sélectionnez le nœud **Génération de code**.  Affectez à **Activation de la régénération minimale** la valeur **Non \(\/Gm\-\)**.  Attribuez également à **Vérifications de base à l'exécution** la valeur **Par défaut**.  
  
     Cliquez sur **OK** pour appliquer les modifications.  
  
4.  Ajoutez une référence au contrôle .NET.  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud de projet MFC01, puis cliquez sur **Ajouter**, **Références**.  Dans la **Page de propriétés**, cliquez sur **Ajouter une nouvelle référence**, sélectionnez **WindowsFormsControlLibrary1** \(sous l'onglet **Projets**\), puis cliquez sur **OK**.  Cette opération ajoute une référence sous la forme d'une option de compilateur [\/FU](../build/reference/fu-name-forced-hash-using-file.md) afin de compiler le programme.  Elle place également une copie de WindowsFormsControlLibrary1.dll dans le dossier de projet \\MFC01\\ afin que le programme s'exécute.  
  
5.  Dans Stdafx.h, recherchez la ligne suivante :  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Au\-dessus de cette ligne, ajoutez les lignes suivantes :  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  Ajoutez le code servant à créer le contrôle managé.  
  
     Commencez par déclarer le contrôle managé.  Dans MFC01Dlg.h, accédez à la déclaration de la classe de boîte de dialogue et ajoutez un membre de données pour le contrôle utilisateur dans la portée Protégé, comme suit :  
  
    ```  
    class CMFC01Dlg : public CDialog  
    {  
       // ...  
       // Data member for the .NET User Control:  
       CWinFormsControl<WindowsFormsControlLibrary1::UserControl1> m_ctrl1;  
    ```  
  
     Fournissez ensuite une implémentation pour le contrôle managé.  Dans MFC01Dlg.cpp, dans la boîte de dialogue de substitution de `CMFC01Dlg::DoDataExchange` générée par l'Assistant Application MFC \(et non `CAboutDlg::DoDataExchange`, qui se trouve dans le même fichier\), ajoutez le code suivant pour créer le contrôle managé et l'associer à l'espace réservé statique IDC\_CTRL1.  
  
    ```  
    void CMFC01Dlg::DoDataExchange(CDataExchange* pDX)  
    {  
       CDialog::DoDataExchange(pDX);  
       DDX_ManagedControl(pDX, IDC_CTRL1, m_ctrl1);  
    }  
    ```  
  
7.  Générez et exécutez le projet.  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur **MFC01**, puis cliquez sur **Définir comme projet de démarrage**.  
  
     Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
     Dans le menu **Déboguer**, cliquez sur **Exécuter sans débogage**.  La boîte de dialogue MFC doit afficher le contrôle Windows Forms.  
  
## Voir aussi  
 [Hébergement d'un contrôle utilisateur Windows Form dans une boîte de dialogue MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)