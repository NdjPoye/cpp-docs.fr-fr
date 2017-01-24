---
title: "Proc&#233;dure pas &#224; pas&#160;: ajout d&#39;un objet D2D &#224; un projet MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "D2D (MFC)"
  - "MFC, D2D"
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
caps.latest.revision: 20
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: ajout d&#39;un objet D2D &#224; un projet MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas à pas explique comment ajouter un objet Direct2D \(D2D\) de base à un projet de bibliothèque MFC \(Microsoft Foundation Class\) Visual C\+\+, puis générer le projet dans une application qui imprime « Hello, world » sur un arrière\-plan dégradé.  
  
 La procédure pas à pas indique comment accomplir les tâches suivantes :  
  
-   Créer une application MFC.  
  
-   Créer un pinceau de couleur unie et un pinceau à dégradé linéaire.  
  
-   Modifier le pinceau à dégradé afin qu'il soit modifié de manière appropriée lorsque la fenêtre est redimensionnée.  
  
-   Implémenter un gestionnaire de dessin D2D.  
  
-   Vérifier les résultats.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## Composants requis  
 Pour effectuer cette procédure pas à pas, vous devez disposer de Visual Studio :  
  
### Pour créer une application MFC  
  
1.  Dans le menu **Fichier**, pointez sur **Nouveau**, puis cliquez sur **Projet**.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, dans le volet gauche sous **Modèles installés**, développez **Visual C\+\+**, puis sélectionnez **Application MFC**.  Dans le volet central, cliquez sur **Application MFC**.  Dans la zone **Nom**, tapez `MFCD2DWalkthrough`.  Cliquez sur **OK**.  
  
3.  Dans l'**Assistant Application MFC**, cliquez sur **Terminer** sans modifier de paramètre.  
  
### Pour créer un pinceau de couleur unie et un pinceau à dégradé linéaire  
  
1.  Dans l'**Explorateur de solutions**, dans le projet **MFCD2DWalkthrough**, dans le dossier **Fichiers d'en\-tête**, ouvrez MFCD2DWalkthroughView.h.  Ajoutez le code suivant à la classe `CMFCD2DWalkthroughView` pour créer trois variables de données.  
  
    ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
    ```  
  
     Enregistrez le fichier et fermez\-le.  
  
2.  Dans le dossier **Fichiers sources**, ouvrez MFCD2DWalkthroughView.cpp.  Dans le constructeur de la classe `CMFCD2DWalkthroughView`, ajoutez le code suivant.  
  
    ```  
    // Enable D2D support for this window:  
    EnableD2DSupport();  
  
    // Initialize D2D resources:  
    m_pBlackBrush = new CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black));  
  
    m_pTextFormat = new CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50);  
    m_pTextFormat->Get()->SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER);  
    m_pTextFormat->Get()->SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER);  
  
    D2D1_GRADIENT_STOP gradientStops[2];  
  
    gradientStops[0].color = D2D1::ColorF(D2D1::ColorF::White);  
    gradientStops[0].position = 0.f;  
    gradientStops[1].color = D2D1::ColorF(D2D1::ColorF::Indigo);  
    gradientStops[1].position = 1.f;  
  
    m_pLinearGradientBrush = new CD2DLinearGradientBrush(GetRenderTarget(),   
        gradientStops, ARRAYSIZE(gradientStops),  
        D2D1::LinearGradientBrushProperties(D2D1::Point2F(0, 0), D2D1::Point2F(0, 0)));  
    ```  
  
     Enregistrez le fichier et fermez\-le.  
  
### Pour modifier le pinceau à dégradé afin qu'il soit modifié de manière appropriée lorsque la fenêtre est redimensionnée  
  
1.  Dans le menu **Projet**, cliquez sur **Assistant Classe**.  
  
2.  Dans l'**Assistant Classe MFC**, sous **Nom de la classe**, sélectionnez `CMFCD2DWalkthroughView`.  
  
3.  Sous l'onglet **Messages**, dans la zone **Messages**, sélectionnez `WM_SIZE`, puis cliquez sur **Ajouter un gestionnaire**.  Cette action ajoute le gestionnaire de messages `OnSize` à la classe `CMFCD2DWalkthroughView`.  
  
4.  Dans la zone **Gestionnaires existants**, sélectionnez `OnSize`.  Cliquez sur **Modifier le code** pour afficher la méthode `CMFCD2DWalkthroughView::OnSize`.  À la fin de la méthode, ajoutez le code suivant.  
  
    ```  
    m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));  
    ```  
  
     Enregistrez le fichier et fermez\-le.  
  
### Pour implémenter un gestionnaire de dessin D2D  
  
1.  Dans le menu **Projet**, cliquez sur **Assistant Classe**.  
  
2.  Dans l'**Assistant Classe MFC**, sous **Nom de la classe**, sélectionnez `CMFCD2DWalkthroughView`.  
  
3.  Sous l'onglet **Messages**, cliquez sur **Ajouter un message personnalisé**.  
  
4.  Dans la boîte de dialogue **Ajouter un message personnalisé**, dans la zone **Messages Windows personnalisé**, tapez `AFX_WM_DRAW2D`.  Dans la zone **Nom du gestionnaire de messages**, tapez `OnDraw2D`.  Sélectionnez l'option **Message inscrit**, puis cliquez sur **OK**.  Cette action ajoute un gestionnaire de messages pour le message `AFX_WM_DRAW2D` à la classe `CMFCD2DWalkthroughView`.  
  
5.  Dans la zone **Gestionnaires existants**, sélectionnez `OnDraw2D`.  Cliquez sur **Modifier le code** pour afficher la méthode `CMFCD2DWalkthroughView::OnDraw2D`.  Utilisez le code suivant pour la méthode `CMFCD2DWalkthroughView::OnDrawD2D`.  
  
    ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
        CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;  
        ASSERT_VALID(pRenderTarget);  
  
        CRect rect;  
        GetClientRect(rect);  
  
        pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);  
        pRenderTarget->DrawText(_T("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);  
  
        return TRUE;  
    }  
    ```  
  
     Enregistrez le fichier et fermez\-le.  
  
### Pour vérifier les résultats  
  
1.  Générez et exécutez l'application.  Un rectangle dégradé doit apparaître et changer lorsque vous redimensionnez la fenêtre. « Hello World\! » doit s'afficher au centre du rectangle.  
  
## Voir aussi  
 [procédures pas à pas](../mfc/walkthroughs-mfc.md)