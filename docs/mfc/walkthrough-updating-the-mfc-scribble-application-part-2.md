---
title: "Proc&#233;dure pas &#224; pas&#160;: mise &#224; jour de l&#39;application Scribble MFC (partie&#160;2) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "procédures pas à pas (C++)"
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
caps.latest.revision: 36
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: mise &#224; jour de l&#39;application Scribble MFC (partie&#160;2)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Partie 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) de sa progression a montré comment ajouter un ruban Office Fluent à l'application classique Scribble.  Cette partie montre comment ajouter des panneaux et des contrôles de ruban que les utilisateurs peuvent utiliser à la place des menus et des commandes.  
  
## Composants requis  
 [Exemples Visual C\+\+](../top/visual-cpp-samples.md)  
  
##  <a name="top"></a> Sections  
 Cette partie de la procédure contient les sections suivantes :  
  
-   [Ajouter de nouveaux panneaux au ruban](#addNewPanel)  
  
-   [Ajouter un volet d'aide sur le ruban](#addHelpPanel)  
  
-   [Ajouter un volet d'écriture sur le ruban](#addPenPanel)  
  
-   [Ajout d'un bouton couleur au ruban.](#addColorButton)  
  
-   [Ajouter un membre de couleur à la classe de document](#addColorMember)  
  
-   [Initialisation les stylets et les préférences](#initPenSave)  
  
##  <a name="addNewPanel"></a> Ajouter de nouveaux panneaux au ruban  
 Les étapes ci\-dessous montrent comment ajouter un panneau **Affichage** qui contient deux cases à cocher qui contrôlent la visibilité de la barre d'outils et de la barre d'état, ainsi qu'un panneau **Fenêtre** qui contient un bouton partagé orienté verticalement qui contrôle la création et la disposition windows \(MDI\) d'interface MDI.  
  
#### Pour ajouter un panneau d'affichage et le panneau d'affichage à la barre du ruban  
  
1.  Créez un panneau appelé `Affichage`, qui a deux cases à cocher qui basculent la barre d'état et la barre d'outils.  
  
    1.  De **Boîte à outils**, faites glisser **Panneau** à la catégorie **Accueil**.  Puis faites glisser deux **Cases à cocher** dans le volet.  
  
    2.  Cliquez sur le panneau pour modifier ses propriétés.  Remplacez la **Légende** par `Affichage`.  
  
    3.  Cliquez sur la première case à cocher pour modifier ses propriétés.  Modifiez **ID** à `ID_VIEW_TOOLBAR` et **Légende** à `Barre d'outils`.  
  
    4.  Cliquez sur la deuxième case à cocher pour modifier ses propriétés.  Modifiez **ID** à `ID_VIEW_STATUS_BAR` et **Légende** à `Barre d'état`.  
  
2.  Créez un panneau nommé `Fenêtre` comportant un bouton partagé.  Lorsqu'un utilisateur clique sur le bouton partagé, un menu contextuel affiche trois commandes qui sont déjà définies dans l'application de dessin à main levée.  
  
    1.  De **Boîte à outils**, faites glisser **Panneau** à la catégorie **Accueil**.  Faites glisser **Bouton** dans le volet.  
  
    2.  Cliquez sur le panneau pour modifier ses propriétés.  Remplacez la **Légende** par `Fenêtre`.  
  
    3.  Cliquez sur le bouton.  Modifiez **Légende** à `Windows`, **Clés** à `s`, **Index de grande taille d'image** à `1`, et **Mode de fractionnement** à `False`.  Cliquez sur le bouton de sélection \(**...**\) en regard de **Éléments de menu** pour ouvrir la boîte de dialogue **Éditeur d'éléments**.  
  
    4.  Cliquer sur **Ajouter** trois fois pour ajouter trois boutons.  
  
    5.  Cliquez sur le premier bouton et modifiez **Légende** à `Nouvelle fenêtre`, et **ID** à `ID_WINDOW_NEW`.  
  
    6.  Cliquez sur le deuxième bouton et modifiez **Légende** à `En cascade`, et **ID** à `ID_WINDOW_CASCADE`.  
  
    7.  Cliquez sur la troisième bouton et modifiez **Légende** à `Mosaïque`, et **ID** à `ID_WINDOW_TILE_HORZ`.  
  
3.  Enregistrez tous les changements, puis générez et exécutez l'application.  Le panneau **Affichage** et de **Fenêtre** doit être affiché.  Cliquez sur les boutons pour vérifier s'ils fonctionnent correctement.  
  
 \[[Sections](#top)\]  
  
##  <a name="addHelpPanel"></a> Ajouter un volet d'aide sur le ruban  
 Maintenant, vous pouvez affecter deux éléments de menu qui sont définis dans l'application de dessin à la main levée aux boutons du ruban qui sont appelés **Rubriques d'aide** et **À propos de dessin à la main levée**.  Les boutons sont ajoutés à un nouveau volet **Aide**nommé.  
  
#### Pour ajouter un panneau d'aide  
  
1.  De **Boîte à outils**, faites glisser **Panneau** à la catégorie **Accueil**.  Puis faites glisser deux **Boutons** dans le volet.  
  
2.  Cliquez sur le panneau pour modifier ses propriétés.  Remplacez la **Légende** par `Aide`.  
  
3.  Cliquez sur le premier bouton.  Modification **Légende** à `Rubriques d'aide`, et **ID** à `ID_HELP_FINDER`.  
  
4.  Cliquez sur le deuxième bouton.  Modification **Légende** à `À propos de dessin à main levée…`, et **ID** à `ID_APP_ABOUT`.  
  
5.  Enregistrez tous les changements, puis générez et exécutez l'application.  Un panneau **Aide** qui contient deux boutons du ruban doit être affiché.  
  
    > [!IMPORTANT]
    >  Lorsque vous cliquez sur le bouton **Rubriques d'aide**, l'application de dessin à main levée ouvre un fichier compressé \(.chm\) *your\_project\_name*intitulé fichier d'aide .chm.  Par conséquent, si votre projet n'est pas nommé dessin à main levée, vous devez renommer le fichier d'aide à votre nom du projet.  
  
 \[[Sections](#top)\]  
  
##  <a name="addPenPanel"></a> Ajouter un volet d'écriture sur le ruban  
 Maintenant, ajoutez un panneau des boutons d'affichage qui contrôlent l'épaisseur et la couleur du stylet.  Ce panneau contient une case à cocher pour basculer entre les stylets épais et légers.  La fonctionnalité similaire à celui de l'élément de menu **Trais épais** dans l'application de dessin à main levée.  
  
 L'application d'origine de dessin à main levée permet à l'utilisateur de sélectionner des largeurs du stylet d'une boîte de dialogue qui s'affiche lorsque l'utilisateur clique sur **Largeur du stylet** dans le menu.  Étant donné que la barre du ruban contient la partie suffisante pour les nouveaux contrôles, vous pouvez remplacer la boîte de dialogue à l'aide de deux zones de liste déroulante sur le ruban.  Une zone de liste déroulante ajuste la largeur du stylet léger et l'autre zone de liste déroulante ajuste la largeur du stylet épais.  
  
#### Pour ajouter un panneau d'écriture et un volet au ruban  
  
1.  De **Boîte à outils**, faites glisser **Panneau** à la catégorie **Accueil**.  Faites glisser **Case à cocher** et deux **Zones de liste déroulante** dans le volet.  
  
2.  Cliquez sur le panneau pour modifier ses propriétés.  Remplacez la **Légende** par `Stylo`.  
  
3.  Activez la case à cocher.  Modification **Légende** à `Utilisation de profondeur`, et **ID** à `ID_PEN_THICK_OR_THIN`.  
  
4.  Cliquez sur la première zone de liste déroulante.  Modification **Légende** à `Le stylet amincissez`, à **ID** à `ID_PEN_THIN_WIDTH`, à **Texte** à `2`, à **Type** à `Liste déroulante`, et **Données** à `1 ; 2 ; 3 ; 4 ; 5 ; 6 ; 7 ; 8 ; 9 ;`.  
  
5.  Cliquez sur la deuxième zone de liste déroulante.  Modification **Légende** à `Stylo fin`, à **ID** à `ID_PEN_THICK_WIDTH`, à **Texte** à `2`, à **Type** à `Liste déroulante`, et **Données** à `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`.  
  
6.  Les nouvelles zones de liste déroulante ne correspondent à aucun élément de menu existant.  Par conséquent, vous devez créer un élément de menu pour chaque option de stylet.  
  
    1.  Dans la fenêtre **Affichage des ressources**, ouvrez la ressource menu en IDR\_SCRIBBTYPE.  
  
    2.  Cliquez sur **Plume** pour ouvrir le menu p**fr**.  Cliquez sur **Tapez ici** et tapez `Thi&stylet n`.  
  
    3.  Cliquez avec le bouton droit sur le texte que vous venez de typé pour ouvrir la fenêtre **Propriétés**, puis modifiez la propriété ID dans `ID_PEN_THIN_WIDTH`.  
  
    4.  Vous devez également créer un gestionnaire d'événements pour chaque élément de menu du stylet.  Cliquez avec le bouton droit sur l'élément de menu **Thi&stylet n** que vous venez de créer puis cliquez sur **Ajouter un gestionnaire d'événements**.  L'**Assistant Gestionnaire d'événements** S'affiche.  
  
    5.  Dans la zone **Liste des classes** dans l'Assistant, sélectionnez **CScribbleDoc** puis cliquez sur **Ajouter**.  Cela crée un gestionnaire d'événements `CScribbleDoc::OnPenThinWidth`nommé.  
  
    6.  Ajoutez le code suivant à `CScribbleDoc::OnPenThinWidth`.  
  
        ```  
        // Get a pointer to the ribbon bar  
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
        ASSERT_VALID(pRibbon);  
        // Get a pointer to the Thin Width combo box  
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(  
           CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));  
        //Get the selected value  
        int nCurSel = pThinComboBox->GetCurSel();  
        if (nCurSel >= 0)  
        {  
           m_nThinWidth = atoi(pThinComboBox->GetItem(nCurSel));  
        }  
        // Create a new pen using the selected width  
        ReplacePen();    
        ```  
  
7.  Ensuite, créez un élément de menu et les gestionnaires d'événements pour le stylet épais.  
  
    1.  Dans la fenêtre **Affichage des ressources**, ouvrez la ressource menu en IDR\_SCRIBBTYPE.  
  
    2.  Cliquez sur **Plume** pour ouvrir le menu stylo.  Cliquez sur **Tapez ici** et tapez `Thic&k stylo` .  
  
    3.  Cliquez avec le bouton droit sur le texte que vous venez de typé pour afficher la fenêtre **Propriétés**.  Modifiez la propriété ID dans `ID_PEN_THICK_WIDTH`.  
  
    4.  Faites un clic droit sur l'élément menu **Stylo épais** que vous venez de créer et cliquez sur **Ajouter un gestionnaire d'événements**.  L'**Assistant Gestionnaire d'événements** S'affiche.  
  
    5.  Dans la zone **Liste des classes** dans l'Assistant, sélectionnez **CScribbleDoc** puis cliquez sur **Ajouter**.  Cela crée un gestionnaire d'événements `CScribbleDoc::OnPenThickWidth`nommé.  
  
    6.  Ajoutez le code suivant à `CScribbleDoc::OnPenThickWidth`.  
  
        ```  
        // Get a pointer to the ribbon bar  
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();  
        ASSERT_VALID(pRibbon);  
        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(  
           CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));  
        // Get the selected value  
        int nCurSel = pThickComboBox->GetCurSel();  
        if (nCurSel >= 0)  
        {  
           m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));  
        }  
        // Create a new pen using the selected width  
        ReplacePen();  
        ```  
  
8.  Enregistrez tous les changements, puis générez et exécutez l'application.  Les Nouveaux boutons et les zones de liste déroulante doivent être affichés.  Essayez d'utiliser des largeurs du stylet à griffonner.  
  
 \[[Sections](#top)\]  
  
##  <a name="addColorButton"></a> Ajouter un bouton de couleur dans le panneau de stylet  
 Ensuite, ajoutez un objet [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) qui permet à l'utilisateur griffonner dans couleurs.  
  
#### Ajouter un bouton de couleur dans le panneau de stylet  
  
1.  Avant d'ajouter le bouton de couleur, créez un élément de menu pour celle\-ci.  Dans la fenêtre **Affichage des ressources**, ouvrez la ressource menu en IDR\_SCRIBBTYPE.  Cliquez sur l'élément de menu **Stylo** pour ouvrir le menu stylo.  Cliquez sur **Tapez ici** et tapez `&Color`.  Cliquez avec le bouton droit sur le texte que vous venez de typé pour afficher la fenêtre **Propriétés**.  Changer l'ID à `ID_PEN_COLOR`.  
  
2.  Ajoutez à présent le bouton de couleur.  De **Boîte à outils**, faites glisser **Bouton de couleur** dans le panneau **Plume**.  
  
3.  Cliquez sur le bouton couleur.  Modifiez **Légende** à `Couleur`, **ID** à `ID_PEN_COLOR`, **Simple Recherchez** à `True`, **Index de grande taille d'image** à `1`, et **Mode de fractionnement** à `False`.  
  
4.  Enregistrez tous les changements, puis générez et exécutez l'application.  Le nouveau bouton de couleur doit être affiché dans le panneau **Plume**.  Toutefois, il ne peut pas être utilisé car il n'a pas encore un gestionnaire d'événements.  Les étapes suivantes indiquent comment ajouter un gestionnaire d'événements pour le bouton de couleur.  
  
 \[[Sections](#top)\]  
  
##  <a name="addColorMember"></a> Ajouter un membre de couleur à la classe de document  
 Étant donné que l'application d'origine de dessin à main levée n'a pas les stylets de couleurs, vous devez entrer une implémentation pour eux.  Pour enregistrer la couleur du stylet du document, ajoutez un membre à la classe de document, `CscribbleDoc.`  
  
#### Ajouter un membre de couleur à la classe de document  
  
1.  Dans scribdoc.h, dans la classe `CScribbleDoc`, recherchez la section `// Attributes`.  Ajoutez les lignes suivantes du code après la définition du membre de données de `m_nThickWidth`.  
  
    ```  
    // Current pen color  
    COLORREF   m_penColor;  
    ```  
  
2.  Chaque document contient une liste de charge que l'utilisateur a déjà dessiné.  Chaque ligne est défini par un objet `CStroke`.  La classe `CStroke` n'inclut pas d'information sur la couleur du stylet.  Par conséquent, vous devez modifier la classe.  Dans scribdoc.h, dans la classe `CStroke`, ajoutez les lignes suivantes du code après la définition du membre de données `m_nPenWidth`.  
  
    ```  
    // Pen color for the stroke  
    COLORREF   m_penColor;  
    ```  
  
3.  Dans scribdoc.h, ajoutez un nouveau constructeur `CStroke` dont les paramètres spécifient une largeur et la couleur.  Ajoutez la ligne suivante après la déclaration `CStroke(UINT nPenWidth);`.  
  
    ```  
    CStroke(UINT nPenWidth, COLORREF penColor);  
    ```  
  
4.  Dans scribdoc.cpp, ajoutez l'implémentation du constructeur `CStroke`.  Ajouter le code suivant après l'implémentation du constructeur `CStroke::CStroke(UINT nPenWidth)`.  
  
    ```  
    // Constructor that uses the document's current width and color  
    CStroke::CStroke(UINT nPenWidth, COLORREF penColor)  
    {  
       m_nPenWidth = nPenWidth;  
       m_penColor = penColor;  
       m_rectBounding.SetRectEmpty();  
    }  
    ```  
  
5.  Modifiez la deuxième ligne de la méthode `CStroke::DrawStroke` comme suit.  
  
    ```  
    if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))  
    ```  
  
6.  Définissez la couleur du stylet par défaut de la classe de document.  Dans scribdoc.cpp, ajoutez les lignes suivantes à `CScribbleDoc::InitDocument`, après l'instruction `m_nThickWidth = 5;`.  
  
    ```  
    // default pen color is black  
    m_penColor = RGB(0,0,0);   
    ```  
  
7.  Dans scribdoc.cpp, modifiez la première ligne de la méthode `CScribbleDoc::NewStroke` au suivant.  
  
    ```  
    CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);  
    ```  
  
8.  Modifiez la dernière ligne de la méthode `CScribbleDoc::ReplacePen` au suivant.  
  
    ```  
    m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);  
    ```  
  
9. Vous avez ajouté le membre `m_penColor` à l'étape précédente.  Maintenant, créez un gestionnaire d'événements pour le bouton de couleur qui définit le membre.  
  
    1.  Dans la fenêtre **Affichage des ressources**, ouvrez la ressource menu en IDR\_SCRIBBTYPE.  
  
    2.  Cliquez avec le bouton droit sur l'élément de menu **Couleur** puis cliquez sur **Ajouter un gestionnaire d'événements...** L'**Assistant Gestionnaire d'événements** S'affiche.  
  
    3.  Dans la zone **Liste des classes** dans l'Assistant, sélectionnez **CScribbleDoc** puis cliquez sur le bouton **Ajouter et éditer**.  Cette action entraîne la création du gestionnaire d'événements `CScribbleDoc::OnPenColor`.  
  
10. Remplacez le talon du gestionnaire d'événements `CScribbleDoc::OnPenColor` par le code suivant.  
  
    ```  
    void CScribbleDoc::OnPenColor()  
    {  
    // Change pen color to reflect color button's current selection  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
    ASSERT_VALID(pRibbon);  
    CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(  
       CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));  
    m_penColor = pColorBtn->GetColor();  
    // Create new pen using the selected color  
    ReplacePen();  
    }  
    ```  
  
11. Enregistrez tous les changements, puis générez et exécutez l'application.  Vous devez pouvoir cliquez sur le bouton de couleur et modifier la couleur du stylet.  
  
 \[[Sections](#top)\]  
  
##  <a name="initPenSave"></a> Initialisation les stylets et les préférences  
 Ensuite, initialisez la couleur et la largeur des stylets.  Enfin, la sauvegarde et chargent un dessin de couleurs dans un fichier.  
  
#### Pour initialiser les contrôles de la barre du ruban  
  
1.  Initialisez les stylets sur la barre du ruban.  
  
     Ajoutez le code suivant à scribdoc.cpp, dans la méthode `CScribbleDoc::InitDocument`, après l'instruction `m_sizeDoc = CSize(200,200)`.  
  
    ```  
    // Reset the ribbon UI to its initial values  
    CMFCRibbonBar* pRibbon =   
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();  
    ASSERT_VALID(pRibbon);  
    CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(  
       CMFCRibbonColorButton,   
       pRibbon->FindByID(ID_PEN_COLOR));  
    // Set ColorButton to black  
    pColorBtn->SetColor(RGB(0,0,0));    
    CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(  
       CMFCRibbonComboBox,   
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));  
    // Set Thin pen combobox to 2  
    pThinComboBox->SelectItem(1);   
    CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(  
       CMFCRibbonComboBox,   
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));  
    // Set Thick pen combobox to 5  
    pThickComboBox->SelectItem(0);  
    ```  
  
2.  Enregistrez une couleur de dessin à un fichier.  Ajoutez la déclaration suivante à scribdoc.cpp, dans la méthode `CStroke::Serialize`, après l'instruction `ar << (WORD)m_nPenWidth;`.  
  
    ```  
    ar << (COLORREF)m_penColor;  
    ```  
  
3.  Enfin, chargez un dessin de couleurs à partir d'un fichier.  Ajoutez la ligne de code suivante, dans la méthode `CStroke::Serialize`, après la déclaration `m_nPenWidth = w;`.  
  
    ```  
    ar >> m_penColor;  
    ```  
  
4.  Maintenant griffonnez dans couleurs et enregistrez votre dessin dans un fichier.  
  
 \[[Sections](#top)\]  
  
## Conclusion  
 Vous avez mis à niveau l'application de dessin à main levée de MFC.  Utilisez cette procédure pas \- à \- pas comme guide lorsque vous modifiez vos applications existantes.  
  
## Voir aussi  
 [procédures pas à pas](../mfc/walkthroughs-mfc.md)   
 [Procédure pas à pas : mise à jour de l'application Scribble MFC \(partie 1\)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)