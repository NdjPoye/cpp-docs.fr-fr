---
title: "Proc&#233;dure pas &#224; pas&#160;: utilisation des nouveaux contr&#244;les d&#39;environnement MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "contrôles d'environnement (MFC)"
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: utilisation des nouveaux contr&#244;les d&#39;environnement MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans cette procédure, vous allez créer une application similaire à l'Explorateur de fichiers.  Vous créerez une fenêtre composée de deux volets.  Le volet gauche contiendra un objet [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) affichant votre Bureau sous forme de vue hiérarchique.  Le volet droit contiendra un [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) affichant les fichiers du dossier sélectionné dans le volet gauche.  
  
## Composants requis  
 Cette procédure considère que vous avez défini [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour utiliser **Paramètres de développement généraux**.  Si vous utilisez un paramètre de développement différent, certaines fenêtres de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] que nous utilisons dans cette procédure ne pourront peut\-être pas être affichées par défaut.  
  
### Pour créer une nouvelle application MFC à l'aide de l'Assistant Application MFC  
  
1.  Utiliser l' **Assistant d'application MFC** pour créer une nouvelle application MFC.  Pour exécuter l'Assistant, dans le menu **Fichier** sélectionnez **Nouveau**, puis sélectionnez **Projet**.  La boîte de dialogue **Nouveau projet** s'affichera.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, développez le nœud **Visual C\+\+** dans le panneau **Types de projet** puis sélectionnez **MFC**.  Dans le volet **Modèles**, sélectionnez ensuite **Application MFC**.  Tapez un nom pour le projet, tel que `MFCShellControls` et cliquez sur **OK**.  L' **Assistant Application MFC** s'affiche.  
  
3.  Dans la boîte de dialogue **Assistant d'application de Windows**, cliquez sur **Suivant**.  Le volet **Type d'application** s'affiche.  
  
4.  Dans le volet **Type d'application**, sous **Type d'application**, désactivez l'option **Documents avec onglet**.  Ensuite, sélectionnez **Mono document \(SDI\)** et sélectionnez **Prise en charge de l'architecture Document\/Vue**.  Sous **Style du projet**, sélectionnez **Visual Studio**, puis dans la liste déroulante **Style visuel et couleurs** sélectionnez **Office 2007 \(Thème bleu\)**.  Laissez toutes les autres options comme elles sont.  Cliquez sur **Suivant** pour afficher le volet **Prise en charge des documents. composés**.  
  
5.  Dans le volet **Prise en charge des documents composés**, sélectionnez **Aucun**.  Cliquez sur **Suivant** pour afficher le volet **Chaînes de modèle de documents**.  
  
6.  N'apportez aucune modification au volet **Chaînes de modèle de documents**.  Cliquez sur **Suivant** pour afficher le volet **Prise en charge des bases de données**.  
  
7.  Dans le volet **Prise en charge des bases de données**, sélectionnez **Aucun** car cette application n'utilise pas de base de données.  Cliquez sur **Suivant** pour afficher le volet **Fonctionnalités de l'interface utilisateur**.  
  
8.  Dans le volet **Fonctionnalités de l'interface utilisateur**, vérifiez que l'option **Utiliser une barre de menus et une barre d'outils** est sélectionnée.  Laissez toutes les autres options comme elles sont.  Cliquez sur **Suivant** pour afficher le volet **Fonctionnalités avancées**.  
  
9. Dans le volet **Fonctionnalités avancées**, sous **Fonctionnalités avancées**, sélectionnez uniquement **Contrôles ActiveX** et **Manifeste des contrôles communs**.  Sous **Volets de fenêtres avancées**, sélectionnez uniquement l'option **Volet de navigation**.  Cela lancera la création par l'assistant du volet à gauche de la fenêtre avec `CMFCShellTreeCtrl` déjà incorporé.  Cliquez sur **Suivant** pour afficher le volet **Classes générées**.  
  
10. Nous n'allons pas apporter des modifications au volet **Classes générées**.  Par conséquent, cliquez sur **Terminer** pour créer votre projet MFC.  
  
11. Vérifiez que l'application a été créée avec succès en la générant et en l'exécutant.  Pour générer l'application, choisissez **Générer** dans le menu **Générer la solution**.  Si l'application est générée avec succès, exécutez\-la en cliquant sur le bouton **Démarrer le débogage** dans le menu **Déboguer**.  
  
     L'assistant crée automatiquement une application comportant une barre de menus standard, une barre d'outils standard, une barre d'état standard, et une barre Outlook à gauche de la fenêtre avec une vue **Dossiers** et une vue **Calendrier**.  
  
### Pour ajouter la liste de contrôle de l'interpréteur de commande à la vue du document  
  
1.  Dans cette section, vous ajouterez une instance de `CMFCShellListCtrl` à la vue que l'Assistant a créée.  Ouvrez le fichier d'en\-tête de vue en double\-cliquant sur MFCShellControlsView.h dans **Explorateur de solutions**.  
  
     Recherchez la directive `#pragma once` en haut du fichier d'en\-tête.  Immédiatement au\-dessous ajoutez ce code pour inclure le fichier d'en\-tête pour `CMFCShellListCtrl`:  
  
    ```  
    #include <afxShellListCtrl.h>  
    ```  
  
     Ajoutez maintenant une variable membre de type `CMFCShellListCtrl`.  D'abord, localisez le commentaire suivant dans le fichier d'en\-tête :  
  
    ```  
    // Generated message map functions  
    ```  
  
     Juste au\-dessus de ces commentaires ajoutez ce code :  
  
    ```  
    private:  
        CMFCShellListCtrl m_wndList;  
    ```  
  
2.  L' **Assistant Application MFC** a déjà créé un objet `CMFCShellTreeCtrl` dans la classe `CMainFrame`, mais est un membre protégé.  Nous accéderons à cet objet ultérieurement.  Par conséquent, créez lui un accesseur maintenant.  Ouvrez le fichier d'en\-tête MainFrm.h en double\-cliquant dessus dans l' **Explorateur de solutions**.  Recherchez le commentaire suivant :  
  
    ```  
    // Attributes  
    ```  
  
     Immédiatement au\-dessous de lui, ajoutez la déclaration de méthode suivante :  
  
    ```  
    public:  
        CMFCShellTreeCtrl& GetShellTreeCtrl();  
    ```  
  
     Ensuite, ouvrez le fichier source MainFrm.cpp en double\-cliquant dessus dans l' **Explorateur de solutions**.  En bas de ce fichier, ajoutez la définition de méthode suivante :  
  
    ```  
    CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()  
    {  
        return m_wndTree;  
    }  
    ```  
  
3.  Maintenant nous mettons à jour la classe `CMFCShellControlsView` pour gérer le message Windows **WM\_CREATE**.  Ouvrez le fichier d'en\-tête de MFCShellControlsView.h et cliquez sur cette ligne de code :  
  
    ```  
    class CMFCShellControlsView : public CView  
    ```  
  
     Dans la fenêtre **Propriétés** , cliquez ensuite sur l'icône **Messages**.  Faites défiler jusqu'à ce que vous trouviez le message **WM\_CREATE**.  Depuis la liste déroulante à coté de **WM\_CREATE**, sélectionnez **\<Ajoutez\> OnCreate**.  Cela crée un gestionnaire de messages pour nous et met automatiquement la table des messages MFC à jour.  
  
     Dans la méthode `OnCreate` nous créerons maintenant notre objet `CMFCShellListCtrl`.  Recherchez la définition de méthode `OnCreate` dans le fichier source du MFCShellControlsView.cpp, puis remplacez son implémentation par le code suivant :  
  
    ```  
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)  
    {  
        if (CView::OnCreate(lpCreateStruct) == -1)  
            return -1;  
  
        CRect rectDummy (0, 0, 0, 0);  
        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,  
            rectDummy, this, 1);  
  
        return 0;  
    }  
    ```  
  
4.  Répétez l'étape précédente sauf pour le message **WM\_SIZE**.  Cela entraîne le rafraichissement de l'affichage de votre application à chaque fois qu'un utilisateur modifie la taille de la fenêtre d'application.  Remplacez la définition de la méthode `OnSize` avec le code suivant:  
  
    ```  
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,  
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);  
    }  
    ```  
  
5.  La dernière étape consiste à connecter les objets `CMFCShellTreeCtrl` et `CMFCShellListCtrl` en utilisant la méthode [CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md).  Après l'appel de cette méthode, `CMFCShellListCtrl` affiche automatiquement le contenu de l'élément sélectionné dans `CMFCShellTreeCtrl`.  Nous ferons cela dans la méthode `OnActivateView`, qui est substituée depuis [CView::OnActivateView](../Topic/CView::OnActivateView.md).  
  
     Dans le fichier d'en\-tête de MFCShellControlsView.h, dans la déclaration de classe `CMFCShellControlsView`, ajoutez la déclaration de méthode suivante :  
  
    ```  
    protected:  
        virtual void OnActivateView(BOOL bActivate,  
            CView* pActivateView,  
            CView* pDeactiveView);  
    ```  
  
     Ensuite, ajoutez la définition de cette méthode au fichier source de MFCShellControlsView.cpp :  
  
    ```  
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,  
        CView* pActivateView,  
        CView* pDeactiveView)   
    {  
        if (bActivate && AfxGetMainWnd() != NULL)  
        {  
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);  
        }  
  
        CView::OnActivateView(bActivate, pActivateView, pDeactiveView);  
    }  
    ```  
  
     Comme nous appelons les méthodes de la classe `CMainFrame`, nous devons ajouter une directive `#include` en haut du fichier source de MFCShellControlsView.cpp :  
  
    ```  
    #include "MainFrm.h"  
    ```  
  
6.  Vérifiez que l'application a été créée avec succès en la générant et en l'exécutant.  Pour générer l'application, choisissez **Générer** dans le menu **Générer la solution**.  Si l'application est générée avec succès, exécutez\-la en cliquant sur le bouton **Démarrer le débogage** dans le menu **Déboguer**.  
  
     Vous devriez maintenant voir les détails de l'élément sélectionné dans `CMFCShellTreeCtrl` dans le volet d'affichage.  Lorsque vous cliquez sur un nœud dans `CMFCShellTreeCtrl`, `CMFCShellListCtrl` sera automatiquement mis à jour.  De même, si vous double\-cliquez sur un dossier dans `CMFCShellListCtrl`, `CMFCShellTreeCtrl` doit être mis à jour automatiquement.  
  
     Cliquez avec le bouton droit sur tout élément dans le contrôle d'arborescence ou dans le contrôle de liste.  Notez que vous obtenez le même menu contextuel que si vous aviez utilisé le vrai Explorateur de fichiers.  
  
## Étapes suivantes  
  
-   L'assistant a créé une barre Outlook avec un volet **Dossiers** et un volet **Calendrier**.  Il n'est probablement pas judicieux d'avoir un volet **Calendrier** dans une fenêtre d'explorateur.  Par conséquent, supprimez ce volet maintenant.  
  
-   `CMFCShellListCtrl` prend en charge les fichiers d'affichage dans différents modes, comme **Grandes icônes**, **Petites icônes**, **Liste**, et **Détails**.  Mettez à jour votre application afin d'implémenter ces fonctionnalités.  Aide : consultez [Exemples Visual C\+\+](../top/visual-cpp-samples.md).  
  
## Voir aussi  
 [procédures pas à pas](../mfc/walkthroughs-mfc.md)