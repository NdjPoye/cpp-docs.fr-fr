---
title: "Proc&#233;dure pas &#224; pas&#160;: ajout d&#39;une animation &#224; un projet MFC | Microsoft Docs"
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
  - "animation (MFC)"
  - "MFC, animation"
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Proc&#233;dure pas &#224; pas&#160;: ajout d&#39;une animation &#224; un projet MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas à pas explique comment ajouter un objet animé de base à un projet de bibliothèque MFC \(Microsoft Foundation Class\) Visual C\+\+.  
  
 La procédure pas à pas indique comment accomplir les tâches suivantes :  
  
-   Créer une application MFC.  
  
-   Ajouter un menu, puis ajouter des commandes permettant de démarrer et d'arrêter une animation.  
  
-   Créer des gestionnaires pour les commandes d'arrêt et de démarrage.  
  
-   Ajouter un objet animé au projet.  
  
-   Centrer l'objet animé dans la fenêtre.  
  
-   Vérifier les résultats.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## Composants requis  
 Pour effectuer cette procédure pas à pas, vous devez disposer de Visual Studio :  
  
### Pour créer une application MFC  
  
1.  Dans le menu **Fichier**, pointez sur **Nouveau**, puis cliquez sur **Projet**.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, dans le volet gauche sous **Modèles installés**, développez **Visual C\+\+**, puis sélectionnez **Application MFC**.  Dans le volet central, cliquez sur **Application MFC**.  Dans la zone **Nom**, tapez `MFCAnimationWalkthrough`.  Cliquez sur **OK**.  
  
3.  Dans la boîte de dialogue **Assistant Application MFC**, vérifiez que le **Type d'application** est **Multidocument \(MDI\)**, que le **Style du projet** est **Visual Studio** et que l'option **Prise en charge de l'architecture Document\/Vue** est sélectionnée.  Cliquez sur **Terminer**.  
  
### Pour ajouter un menu, puis ajouter des commandes permettant de démarrer et d'arrêter une animation  
  
1.  Dans le menu **Affichage**, pointez sur **Autres fenêtres**, puis cliquez sur **Affichage des ressources**.  
  
2.  Dans **Affichage des ressources**, naviguez jusqu'au dossier **Menu** et ouvrez\-le.  Double\-cliquez sur la ressource `IDR_MFCAnimationWalTYPE` pour l'ouvrir en vue de la modifier.  
  
3.  Sur la barre de menus, dans la zone **Tapez ici**, tapez `A&nimation` pour créer un menu Animation.  
  
4.  Sous **Animation**, dans la zone **Tapez ici**, tapez `Démarrer &En avant` pour créer une commande Démarrer en avant.  
  
5.  Sous **Démarrer en avant**, dans la zone **Tapez ici**, tapez `Démarrer &En arrière`.  
  
6.  Sous **Démarrer en arrière**, dans la zone **Tapez ici**, tapez `S&top` pour créer une commande Arrêter.  
  
7.  Enregistrez le fichier MFCAnimationWalkthrough.rc et fermez\-le.  
  
8.  Dans l'**Explorateur de solutions**, double\-cliquez sur MainFrm.cpp pour l'ouvrir en vue de le modifier.  Dans la méthode `CMainFrame::OnCreate`, localisez la section comportant plusieurs appels à `lstBasicCommands.AddTail`.  Juste après cette section, ajoutez le code suivant.  
  
    ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);  
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);  
    ```  
  
9. Enregistrez le fichier et fermez\-le.  
  
### Pour créer des gestionnaires pour les commandes d'arrêt et de démarrage  
  
1.  Dans le menu **Projet**, cliquez sur **Assistant Classe**.  
  
2.  Dans l'**Assistant Classe MFC**, sous **Nom de la classe**, sélectionnez `CMFCAnimationWalkthroughView`.  
  
3.  Sous l'onglet **Commandes**, dans la zone **ID d'objet**, sélectionnez `ID_ANIMATION_STARTFORWARD`, puis, dans la zone **Messages**, sélectionnez `COMMAND`.  Cliquez sur **Ajouter un gestionnaire**.  
  
4.  Dans la boîte de dialogue **Ajout de fonction membre**, cliquez sur **OK**.  
  
5.  Dans la zone **ID d'objet**, sélectionnez `ID_ANIMATION_STARTBACKWARD`, puis, dans la zone **Messages**, sélectionnez `COMMAND`.  Cliquez sur **Ajouter un gestionnaire**.  
  
6.  Dans la boîte de dialogue **Ajout de fonction membre**, cliquez sur **OK**.  
  
7.  Dans la zone **ID d'objet**, sélectionnez `ID_ANIMATION_STOP`, puis, dans la zone **Messages**, sélectionnez `COMMAND`.  Cliquez sur **Ajouter un gestionnaire**, puis sur **OK**.  
  
8.  Dans la boîte de dialogue **Ajout de fonction membre**, cliquez sur **OK**.  
  
9. Dans l'**Assistant Classe MFC**, cliquez sur **OK**.  
  
10. Enregistrez MFCAnimationWalkthroughView.cpp, fichier ouvert dans l'éditeur, mais ne le fermez pas.  
  
### Pour ajouter un objet animé au projet  
  
1.  Dans l'Explorateur de solutions, double\-cliquez sur MFCAnimationWalkthroughView.h pour l'ouvrir en vue de le modifier.  Juste avant la définition de la classe `CMFCAnimationWalkthroughView`, ajoutez le code suivant pour créer un contrôleur d'animation personnalisé destiné à gérer les conflits de planification avec l'objet d'animation.  
  
    ```  
    class CCustomAnimationController : public CAnimationController  
    {  
    public:  
        CCustomAnimationController()  
        {  
        }  
  
        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled, CAnimationGroup* pGroupNew, UI_ANIMATION_PRIORITY_EFFECT priorityEffect)  
        {  
            return TRUE;  
        }  
    };  
    ```  
  
2.  À la fin de la classe `CMFCAnimationWalkthroughView`, ajoutez le code suivant.  
  
    ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
    ```  
  
3.  Après la ligne `DECLARE_MESSAGE_MAP()`, ajoutez le code suivant.  
  
    ```  
    void Animate(BOOL bDirection);  
    ```  
  
4.  Enregistrez le fichier et fermez\-le.  
  
5.  Dans MFCAnimationWalkthroughView.cpp, en haut du fichier, après les instructions `#include`, mais avant les méthodes de classe, ajoutez le code suivant.  
  
    ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
    ```  
  
6.  À la fin du constructeur de `CMFCAnimationWalkthroughView`, ajoutez le code suivant.  
  
    ```  
    m_animationController.EnableAnimationTimerEventHandler();  
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);  
  
    m_animationColor = RGB(255, 255, 255);  
    m_animationRect = CRect(0, 0, 0, 0);  
  
    m_animationColor.SetID(-1, nAnimationGroup);  
    m_animationRect.SetID(-1, nAnimationGroup);  
  
    m_animationController.AddAnimationObject(&m_animationColor);  
    m_animationController.AddAnimationObject(&m_animationRect);  
    ```  
  
7.  Recherchez la méthode `CAnimationWalthroughView::PreCreateWindow`, puis remplacez\-la par le code suivant.  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
    {  
        // TODO: Modify the Window class or styles here by modifying  
        //  the CREATESTRUCT cs  
  
        m_animationController.SetRelatedWnd(this);  
        return CView::PreCreateWindow(cs);  
    }  
    ```  
  
8.  Recherchez la méthode `CAnimationWalkthroughView::OnDraw`, puis remplacez\-la par le code suivant.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
    {  
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();  
        ASSERT_VALID(pDoc);  
        if (!pDoc)  
            return;  
  
        // TODO: add draw code for native data here  
        CMemDC dcMem(*pDC, this);  
        CDC& dc = dcMem.GetDC();  
  
        CRect rect;  
        GetClientRect(rect);  
  
        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));  
  
        CString strRGB;  
        strRGB.Format(_T("Fill Color is: %d; %d; %d"), GetRValue(m_animationColor), GetGValue(m_animationColor), GetBValue(m_animationColor));  
  
        dc.DrawText(strRGB, rect, DT_CENTER);  
        rect.top += nInfoAreaHeight;  
  
        CBrush br;  
  
        br.CreateSolidBrush(m_animationColor);  
        CBrush* pBrushOld = dc.SelectObject(&br);  
  
        dc.Rectangle((CRect)m_animationRect);  
        dc.SelectObject(pBrushOld);  
    }  
    ```  
  
9. À la fin du fichier, ajoutez le code suivant.  
  
    ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
    {  
        static UI_ANIMATION_SECONDS duration = 3;  
        static DOUBLE dblSpeed = 35.;  
        static BYTE nStartColor = 50;  
        static BYTE nEndColor = 255;  
  
        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;  
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;  
  
        CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);  
        CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);  
        CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);  
  
        m_animationColor.AddTransition(pRedTransition, pGreenTransition, pBlueTransition);  
  
        CRect rectClient;  
        GetClientRect(rectClient);  
        rectClient.top += nInfoAreaHeight;  
  
        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;  
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;  
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;  
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;  
  
        CLinearTransition* pLeftTransition = new CLinearTransition(duration, nLeftFinal);  
        CLinearTransition* pTopTransition = new CLinearTransition(duration, nTopFinal);  
        CLinearTransition* pRightTransition = new CLinearTransition(duration, nRightFinal);  
        CLinearTransition* pBottomTransition = new CLinearTransition(duration, nBottomFinal);  
  
        m_animationRect.AddTransition(pLeftTransition, pTopTransition, pRightTransition, pBottomTransition);  
  
        CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();  
        CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup, pBlueTransition);  
  
        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);  
  
        m_animationController.AnimateGroup(nAnimationGroup);  
    }  
    ```  
  
10. Dans le menu **Projet**, cliquez sur **Assistant Classe**.  
  
11. Dans l'**Assistant Classe MFC**, sous **Nom de la classe**, sélectionnez `CMFCAnimationWalkthroughView`.  
  
12. Sous l'onglet **Messages**, dans la zone **Messages**, sélectionnez `WM_ERASEBKGND`, cliquez sur **Ajouter un gestionnaire**, puis sur **OK**.  
  
13. Dans MFCAnimationWalkthroughView.cpp, remplacez l'implémentation de `OnEraseBkgnd` par le code suivant pour réduire le scintillement dans l'objet animé lorsqu'il est redessiné.  
  
    ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
    {  
        return TRUE;  
    }  
    ```  
  
14. Remplacez les implémentations de `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward` et de `CMFCAnimationWalkthroughView::OnAnimationStop` par le code suivant.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()  
    {  
        Animate(TRUE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()  
    {  
        Animate(FALSE);  
    }  
  
    void CMFCAnimationWalkthroughView::OnAnimationStop()  
    {  
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();  
        if (pManager != NULL)  
        {  
            pManager->AbandonAllStoryboards();  
        }  
    }  
  
    ```  
  
15. Enregistrez le fichier et fermez\-le.  
  
### Pour centrer l'objet animé dans la fenêtre  
  
1.  Dans l'**Explorateur de solutions**, double\-cliquez sur MFCAnimationWalkthroughView.h pour l'ouvrir en vue de le modifier.  À la fin de la classe `CMFCAnimationWalkthroughView`, juste après la définition de `m_animationRect`, ajoutez le code suivant.  
  
    ```  
    BOOL m_bCurrentDirection;  
    ```  
  
2.  Enregistrez le fichier et fermez\-le.  
  
3.  Dans le menu **Projet**, cliquez sur **Assistant Classe**.  
  
4.  Dans l'**Assistant Classe MFC**, sous **Nom de la classe**, sélectionnez `CMFCAnimationWalkthroughView`.  
  
5.  Sous l'onglet **Messages**, dans la zone **Messages**, sélectionnez `WM_SIZE`, cliquez sur **Ajouter un gestionnaire**, puis sur **OK**.  
  
6.  Dans MFCAnimationWalkthroughView.cpp, remplacez le code de `CMFCAnimationWalkthroughView::OnSize` par le code suivant.  
  
    ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);  
  
        CRect rect;  
        GetClientRect(rect);  
        rect.top += nInfoAreaHeight;  
  
        CRect rectAnim = m_animationRect;  
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,   
                                rect.CenterPoint().y - rectAnim.Height() / 2),   
                                rectAnim.Size());  
  
        if (m_animationController.IsAnimationInProgress())  
        {  
            Animate(m_bCurrentDirection);  
        }  
    }  
    ```  
  
7.  Au début du constructeur de `CMFCAnimationWalkthroughView`, ajoutez le code suivant.  
  
    ```  
    m_bCurrentDirection = TRUE;  
    ```  
  
8.  Au début de la méthode `CMFCAnimationWalkthroughView::Animate`, ajoutez le code suivant.  
  
    ```  
    m_bCurrentDirection = bDirection;  
    ```  
  
9. Enregistrez le fichier et fermez\-le.  
  
### Pour vérifier les résultats  
  
1.  Générez et exécutez l'application.  Dans le menu **Animation**, cliquez sur **Démarrer en avant**.  Un rectangle doit s'afficher, puis remplir la zone centrale.  Lorsque vous cliquez sur **Démarrer en arrière**, l'animation doit s'inverser et, lorsque vous cliquez sur **Arrêter**, elle doit s'arrêter.  La couleur de remplissage du rectangle doit évoluer à mesure que l'animation progresse et la couleur en cours doit s'afficher en haut de la fenêtre d'animation.  
  
## Voir aussi  
 [procédures pas à pas](../mfc/walkthroughs-mfc.md)