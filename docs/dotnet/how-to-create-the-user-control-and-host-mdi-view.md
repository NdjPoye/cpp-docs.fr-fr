---
title: "Comment&#160;: cr&#233;er le contr&#244;le utilisateur et h&#233;berger l&#39;affichage MDI | Microsoft Docs"
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
  - "MFC (C++), contrôles Windows Forms"
  - "Windows Forms (C++), prise en charge des MFC"
ms.assetid: 625b5821-f923-4701-aca0-c1a4ceca4f63
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# Comment&#160;: cr&#233;er le contr&#244;le utilisateur et h&#233;berger l&#39;affichage MDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les étapes suivantes indiquent comment créer un contrôle utilisateur .NET Framework, comment le créer dans une bibliothèque de classes de contrôle \(en particulier un projet de bibliothèque de contrôles Windows\), puis compiler le projet dans un assembly.  Le contrôle peut ensuite être consommé à partir d'une application MFC qui utilise des classes dérivées de la [CView Class](../mfc/reference/cview-class.md) et de la [CWinFormsView Class](../mfc/reference/cwinformsview-class.md).  
  
 Pour plus d'informations sur la création d'un contrôle utilisateur Windows Forms et la création d'une bibliothèque de classes de contrôle, voyez [How to: Author User Controls](../Topic/How%20to:%20Author%20Composite%20Controls.md).  
  
> [!NOTE]
>  Dans certains cas, des contrôles Windows Forms \(comme un contrôle Grid tiers\) peuvent ne pas se comporter de façon fiable au sein de l'application MFC qui les héberge.  Une solution de contournement conseillée sera de placer un contrôle utilisateur Windows Forms dans l'application MFC et de placer le contrôle Grid tiers à l'intérieur du contrôle utilisateur.  
  
 Cette procédure suppose que vous avez créé un projet de bibliothèque de contrôles Windows Forms nommé WindowsFormsControlLibrary1, selon la procédure exposée dans [Comment : créer le contrôle utilisateur et l'héberger dans une boîte de dialogue](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
### Pour créer l'application MFC hôte  
  
1.  Créez un projet d'application MFC.  
  
     Dans le menu **Fichier**, sélectionnez **Nouveau**, puis cliquez sur **Projet**.  Dans le dossier **Visual C\+\+**, sélectionnez **Application MFC**.  
  
     Dans la zone **Nom**, entrez `MFC02` et remplacez le paramètre **Solution** par **Ajouter à la solution**.  Cliquez sur **OK**.  
  
     Dans l'**Assistant Application MFC**, acceptez toutes les valeurs par défaut, puis cliquez sur **Terminer**.  Cela crée une application MFC avec une interface multidocument.  
  
2.  Configurez le projet pour la prise en charge du Common Language Runtime \(CLR\).  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud du projet `MFC01`, puis sélectionnez **Propriétés** dans le menu contextuel.  La boîte de dialogue **Pages de propriétés** s'affiche.  
  
     Sous **Propriétés de configuration**, sélectionnez **Général**.  Sous la section **Paramètres par défaut du projet**, attribuez à **Prise en charge du Common Language Runtime** la valeur **Prise en charge du Common Language Runtime \(\/clr\)**.  
  
     Sous **Propriétés de configuration**, développez **C\/C\+\+**, puis cliquez sur le nœud **Général**.  Affectez à **Format des informations de débogage** la valeur **Base de données du programme \(\/Zi\)**.  
  
     Cliquez sur le nœud **Génération de code**.  Affectez à **Activation de la régénération minimale** la valeur **Non \(\/Gm\-\)**.  Attribuez également à **Vérifications de base à l'exécution** la valeur **Par défaut**.  
  
     Cliquez sur **OK** pour enregistrer les modifications apportées.  
  
3.  Dans stdafx.h, ajoutez la ligne suivante :  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
4.  Ajoutez une référence au contrôle .NET.  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le nœud du projet `MFC02` et sélectionnez **Ajouter**, **Références**.  Dans **Page de propriétés**, cliquez sur **Ajouter une nouvelle référence**, sélectionnez WindowsFormsControlLibrary1 \(sous l'onglet **Projets**\) et cliquez sur **OK**.  Cela ajoute une référence sous la forme d'une option du compilateur [\/FU](../build/reference/fu-name-forced-hash-using-file.md) afin que le programme exécute la compilation ; cela copie également WindowsFormsControlLibrary1.dll dans le répertoire du projet `MFC02` afin que le programme s'exécute.  
  
5.  Dans stdafx.h, recherchez la ligne suivante :  
  
    ```  
    #endif // _AFX_NO_AFXCMN_SUPPORT   
    ```  
  
     Ajoutez ces lignes au\-dessus :  
  
    ```  
    #include <afxwinforms.h>   // MFC Windows Forms support  
    ```  
  
6.  Modifiez la classe d'affichage afin qu'elle hérite de [CWinFormsView](../mfc/reference/cwinformsview-class.md).  
  
     Dans MFC02View.h, remplacez [CView](../mfc/reference/cview-class.md) par [CWinFormsView](../mfc/reference/cwinformsview-class.md) afin que le code apparaisse comme ceci :  
  
    ```  
    class CMFC02View : public CWinFormsView  
    {  
    };  
    ```  
  
     Si vous souhaitez ajouter des affichages supplémentaires à votre application MDI, vous devez appeler [CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md) pour chaque affichage que vous créez.  
  
7.  Modifiez le fichier MFC02View.cpp pour transformer CView en CWinFormsView dans la macro IMPLEMENT\_DYNCREATE et la table des messages, puis remplacez le constructeur vide existant par le constructeur indiqué dessous :  
  
    ```  
    IMPLEMENT_DYNCREATE(CMFC02View, CWinFormsView)  
  
    CMFC02View::CMFC02View(): CWinFormsView(WindowsFormsControlLibrary1::UserControl1::typeid)   
    {  
    }  
    BEGIN_MESSAGE_MAP(CMFC02View, CWinFormsView)  
    //leave existing body as is  
    END_MESSAGE_MAP()  
    ```  
  
8.  Générez et exécutez le projet.  
  
     Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur MFC02, puis sélectionnez **Définir comme projet de démarrage**.  
  
     Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
     Dans le menu **Déboguer**, cliquez sur **Exécuter sans débogage**.  
  
## Voir aussi  
 [Hébergement d'un contrôle utilisateur Windows Forms en tant que vue MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)