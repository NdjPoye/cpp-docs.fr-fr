---
title: "TN030&#160;: personnalisation de l&#39;impression et de l&#39;aper&#231;u avant impression | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.print"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "personnaliser l'impression et l'aperçu avant impression"
  - "aperçu avant impression, personnaliser"
  - "imprimer (MFC), vues"
  - "imprimer des vues"
  - "TN030"
ms.assetid: 32744697-c91c-41b6-9a12-b8ec01e0d438
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN030&#160;: personnalisation de l&#39;impression et de l&#39;aper&#231;u avant impression
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit le processus de personnalisation de l'impression et d'aperçu avant impression et décrit les objectifs des routines de rappel utilisées dans `CView` et les routines de rappel et méthodes de **CPreviewView**.  
  
## Le problème  
 MFC offre une solution complète pour la plupart des besoins d'impression et d'aperçu avant impression.  Dans la plupart des cas, peu de code supplémentaire est nécessaire pour obtenir une perspective pouvant imprimer et fournir un aperçu.  Toutefois, il existe des méthodes pour optimiser l'impression qui nécessitent un effort important de la part du développeur, et certaines applications doivent ajouter des éléments d'interface utilisateur spécifiques au mode aperçu avant impression.  
  
## L'impression efficace  
 Lorsqu'une application MFC imprime à l'aide des méthodes standard, Windows exécute tous les appels à Graphical Device Interface \(GDI\) dans un métafichier en mémoire.  Lorsque `EndPage` est appelé, Windows joue un métafichier une fois pour chaque bande physique dont l'imprimante a besoin pour imprimer une page.  Lors de ce rendu, GDI appelle fréquemment la procédure d'arrêt pour déterminer si il doit continuer.  En général, la procédure d'arrêt permet aux messages d'être traités de façon à ce que l'utilisateur puisse interrompre le travail d'impression à l'aide d'un dialogue d'impression.  
  
 Malheureusement, cela peut ralentir le processus d'impression.  Si l'impression dans votre application doit être plus rapide que ce qui peut être atteint en utilisant la technique standard, vous devez implémenter une réalisation de bandes manuelle.  
  
## Contrôle d'impression  
 Afin de réaliser les bandes manuellement, vous devez re\-implémenter la boucle d'impressions pour que `OnPrint` soit appelée plusieurs fois par page \(une fois par bande\).  La boucle d'impression est implémentée dans la fonction **OnFilePrint** dans viewprnt.cpp.  Dans votre classe dérivée de `CView`, vous surchargez cette fonction afin que l'entrée de la table des messages pour la gestion de la commande imprimer appelle votre fonction d'impression.  Copiez la routine **OnFilePrint** et modifiez la boucle d'impression pour implémenter la bande.  Vous souhaiterez probablement également mentionner le rectangle de bande dans les fonctionnalités d'impression pour pouvoir optimiser le dessin selon la section de la page en cours d'impression.  
  
 Ensuite, vous devez fréquemment appeler `QueryAbort` lors du tracé de la bande.  Sinon, la procédure d'arrêt n'est pas appelée et l'utilisateur ne pourra pas annuler le travail d'impression.  
  
## Aperçu avant impression : Papier électronique avec l'interface utilisateur  
 L'aperçu avant impression, en fait, tente de convertir l'affichage en une émulation d'une imprimante.  Par défaut, la zone client de la fenêtre principale est utilisée pour afficher une ou deux pages entièrement dans la fenêtre.  L'utilisateur peut zoomer sur la zone de la page pour l'afficher plus en détail.  Avec une prise en charge supplémentaire, l'utilisateur peut même être autorisé à modifier le document en mode aperçu.  
  
## Personnaliser l'aperçu avant impression  
 Cette remarque traite uniquement d'un aspect de modification de l'aperçu avant impression : l'ajout d'une interface utilisateur en mode aperçu.  D'autres modifications sont possibles, mais sont hors de portée de cette discussion.  
  
## Pour ajouter une interface utilisateur en mode aperçu  
  
1.  Dérivez une classe d'affichage de **CPreviewView**.  
  
2.  Ajouter des gestionnaires de commandes pour les aspects de l'interface utilisateur souhaités.  
  
3.  Si vous ajoutez des aspects visuels à l'affichage, outrepassez `OnDraw` et effectuez votre dessin après avoir appelé **CPreviewView::OnDraw.**  
  
## OnFilePrintPreview  
 Il s'agit du gestionnaire de commandes pour l'aperçu avant impression.  Son une implémentation par défaut est :  
  
```  
void CView::OnFilePrintPreview()  
{  
    // In derived classes, implement special window handling here  
    // Be sure to Unhook Frame Window close if hooked.  
  
    // must not create this on the frame. Must outlive this function  
    CPrintPreviewState* pState = new CPrintPreviewState;  
  
    if (!DoPrintPreview(AFX_IDD_PREVIEW_TOOLBAR, this,  
                RUNTIME_CLASS(CPreviewView), pState))  
    {  
        // In derived classes, reverse special window handling  
        // here for Preview failure case  
  
        TRACE0("Error: DoPrintPreview failed");  
        AfxMessageBox(AFX_IDP_COMMAND_FAILURE);  
        delete pState;      // preview failed to initialize,   
                    // delete State now  
    }  
}  
```  
  
 **DoPrintPreview** masquera le volet principal de l'application.  Les barres de commandes, telles que la barre d'état, peuvent être conservées en les spécifiant dans le membre pState\-\>**dwStates** \(il s'agit d'un masque de bits et les bits des barres de contrôles sont définis par **AFX\_CONTROLBAR\_MASK**\(AFX\_IDW\_MYBAR\)\).  Le pState\-\>**nIDMainPane** de fenêtre est la fenêtre qui est automatiquement masquée et montrée.  **DoPrintPreview** crée ensuite une barre d'icônes pour l'interface utilisateur standard d'aperçu.  Si une gestion spéciale de la fenêtre est nécessaire, par exemple pour masquer ou afficher d'autres fenêtres, ceci doit être réalisé avant que **DoPrintPreview** soit appelé.  
  
 Par défaut, lorsque l'aperçu avant impression termine, il retourne les barres de contrôles à leurs états d'origine et le volet principal à visible.  Si une gestion spéciale est nécessaire, elle doit être créée dans une substitution de **EndPrintPreview.** Si **DoPrintPreview** échoue, fournissez également une gestion particulière.  
  
 DoPrintPreview est appelé avec :  
  
-   L'ID de ressource du modèle de boîte de dialogue pour la barre d'outils d'aperçu.  
  
-   Un pointeur vers la vue pour effectuer une impression pour l'aperçu avant impression.  
  
-   La classe d'exécution de la classe d'aperçu.  Ce sera créé dynamiquement dans DoPrintPreview.  
  
-   Le pointeur de CPrintPreviewState.  Notez que la structure de CPrintPreviewState \(ou la structure dérivée si l'application a besoin de plus d'état conservé\) ne doit *pas* être créée dans le cadre.  DoPrintPreview est non modal et cette structure doit survivre jusqu'à ce qu'EndPrintPreview soit appelé.  
  
    > [!NOTE]
    >  Si une vue ou une classe d'affichage distincte est nécessaire pour la prise en charge de l'impression, un pointeur vers l'objet doit être passé comme deuxième paramètre.  
  
## EndPrintPreview  
 Cela est appelé pour quitter le mode aperçu avant impression.  Il est souvent souhaitable de passer à la page du document qui a été affichée en dernier dans l'aperçu avant impression.  **EndPrintPreview** est l'occasion de l'application de réaliser ceci.  Le membre pInfo\-\>`m_nCurPage` est la page qui a été affichée en dernier \(à l'extrême gauche si deux pages sont affichées\), et le pointeur est une indication quant à la position d'intérêt de l'utilisateur dans la page.  Comme la structure de la vue de l'application n'est pas connue par l'infrastructure, vous devez fournir un code pour se déplacer vers le point sélectionné.  
  
 Vous devez exécuter la plupart des actions avant d'appeler **CView::EndPrintPreview**.  Cet appel inverse les effets de **DoPrintPreview** et supprime pView, pDC, et pInfo.  
  
```  
// Any further cleanup should be done here.  
CView::EndPrintPreview(pDC, pInfo, point, pView);  
```  
  
## CWinApp::OnFilePrintSetup  
 Il doit être mappé pour l'élément de menu de configuration de l'impression.  Dans la plupart des cas, il n'est pas nécessaire de remplacer l'implémentation.  
  
## Nomenclature de page  
 Un autre problème est celui de la pagination et de l'ordre des pages.  Pour les applications simples de type de traitement de texte, il s'agit d'un problème simple.  La plupart des systèmes d'aperçu avant impression supposent que chaque page imprimée correspond à une page dans le document.  
  
 En essayant de fournir une solution généralisée, il y a plusieurs éléments à prendre en considération.  Imaginez un système de CAO.  L'utilisateur a un dessin qui couvre plusieurs feuilles de taille E.  Sur un traceur de taille E \(ou un plus petit, mis à l'échelle\), la numérotation des pages est comme dans le cas simple.  Mais sur une imprimante laser, imprimant 16 pages de taille A par feuille, qu'est\-ce que l'aperçu avant impression considère comme une « page » ?  
  
 Comme le note le paragraphe préliminaire, l'aperçu avant impression agit comme une imprimante.  Par conséquent, il pourra voir ce qui sortirait de l'imprimante particulière qui est sélectionnée.  Il appartient à la vue de déterminer quelle image est imprimée sur chaque page.  
  
 La chaîne de description de pages dans la structure `CPrintInfo` fournit un moyen d'afficher le numéro de page à l'utilisateur si elle peut être représentée sous forme d'un nombre par page \(comme dans « page 1 " ou « pages 1\-2 »\). Cette chaîne est utilisée par l'implémentation par défaut de **CPreviewView::OnDisplayPageNumber**.  Si une vue différente est nécessaire, il est possible de remplacer cette fonction virtuelle pour fournir, par exemple, « Feuille1, Sections A, B ».  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)