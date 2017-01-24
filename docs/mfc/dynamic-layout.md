---
title: "Disposition dynamique | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
caps.latest.revision: 7
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Disposition dynamique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes MFC de [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] vous permettent de créer des boîtes de dialogue redimensionnables par l'utilisateur et de contrôler la façon dont la disposition s'ajuste aux changements de taille.  Par exemple, vous pouvez ancrer des boutons au bas d'une boîte de dialogue sur le bord inférieur afin qu'ils restent toujours affichés à cet endroit.  Vous pouvez également créer des contrôles, tels que des zones de liste, des zones d'édition et des champs de texte, qui s'agrandissent quand l'utilisateur agrandit la boîte de dialogue.  
  
## Spécification des paramètres de disposition dynamique pour une boîte de dialogue MFC  
 Quand l'utilisateur redimensionne une boîte de dialogue, les contrôles qui y figurent peuvent être redimensionnés ou déplacés dans les directions X et Y.  Le changement de la taille ou de l'emplacement d'un contrôle quand l'utilisateur redimensionne une boîte de dialogue est appelé disposition dynamique.  Par exemple, voici une boîte de dialogue initiale, avant un redimensionnement :  
  
 ![Boîte de dialogue avant redimensionnement.](../mfc/media/mfcdynamiclayout4.png "MFCDynamicLayout4")  
  
 Après le redimensionnement de la boîte de dialogue, nous voyons que la zone de liste a été agrandie pour afficher davantage d'éléments et que les boutons ont été déplacés vers le coin inférieur droit :  
  
 ![Boîte de dialogue après redimensionnement.](../mfc/media/mfcdynamiclayout5.png "MFCDynamicLayout5")  
  
 Vous pouvez contrôler la disposition dynamique en configurant chaque contrôle dans l'éditeur de ressources de l'IDE, ou le faire par programme en accédant à l'objet CMFCDynamicLayout d'un contrôle spécifique et en définissant ses propriétés.  
  
### Définition des propriétés de disposition dynamique dans l'éditeur de ressources  
 L'éditeur de ressources vous permet de définir le comportement de disposition dynamique pour une boîte de dialogue sans avoir à écrire de code.  
  
##### Pour définir les propriétés de disposition dynamique dans l'éditeur de ressources  
  
1.  Dans un projet MFC ouvert, ouvrez la boîte de dialogue à configurer dans l'éditeur de boîtes de dialogue.  
  
     ![Ouvrez la boîte de dialogue dans l'éditeur de ressources.](../mfc/media/mfcdynamiclayout3.png "MFCDynamicLayout3")  
  
2.  Sélectionnez un contrôle et, dans la fenêtre Propriétés, définissez ses propriétés de disposition dynamique.  Dans la fenêtre Propriétés, la section **Disposition dynamique** affiche les propriétés **Type de déplacement**, **Type de redimensionnement** et, en fonction des valeurs sélectionnées pour ces propriétés, des propriétés spécifiques qui définissent la façon dont les contrôles changent d'emplacement ou de taille.  **Type de déplacement** détermine la façon dont un contrôle est déplacé quand la taille de la boîte de dialogue est modifiée. **Type de redimensionnement** détermine comment la taille d'un contrôle s'ajuste à celle de la boîte de dialogue.  Les propriétés **Type de déplacement** et **Type de redimensionnement** peuvent être définies sur **Horizontal**, **Vertical**, **Les deux** ou **Aucun** en fonction des dimensions que vous souhaitez modifier de manière dynamique.  Le type Horizontal correspond à la dimension X et le type Vertical, à la dimension Y.  
  
3.  Pour créer un contrôle de taille fixe qui s'affiche toujours en bas à droite, comme c'est généralement le cas pour les boutons **OK** et **Annuler**, définissez **Type de redimensionnement** sur **Aucun** et **Type de déplacement** sur **Les deux**.  Définissez les valeurs **Déplacement X** et **Déplacement Y** sous **Type de déplacement** sur 100 %. Ainsi, le contrôle s'affichera toujours à la même distance du coin inférieur droit.  
  
     ![Disposition dynamique](../mfc/media/mfcdynamiclayout1.png "MFCDynamicLayout1")  
  
4.  Supposons que vous voulez aussi créer un contrôle qui s'agrandit à mesure que la boîte de dialogue elle\-même est agrandie.  En règle générale, un utilisateur agrandit une boîte de dialogue pour développer une zone d'édition multiligne et augmenter la taille de la zone de texte, ou il développe un contrôle de liste pour afficher davantage de données.  Dans ce cas, définissez **Type de redimensionnement** sur Les deux et **Type de déplacement** sur Aucun.  Ensuite, définissez **Redimensionnement X** et **Redimensionnement Y** sur 100.  
  
     ![Paramètres de disposition dynamique](../mfc/media/mfcdynamiclayout2.png "MFCDynamicLayout2")  
  
5.  Faites des essais avec d'autres valeurs qui pourraient convenir pour vos contrôles.  Pour une boîte de dialogue contenant une zone de texte d'une seule ligne, vous pouvez uniquement définir **Type de redimensionnement** à la valeur **Horizontal**, par exemple.  
  
### Définition des propriétés de disposition dynamique par programme  
 La procédure précédente permet de spécifier les propriétés de disposition dynamique d'une boîte de dialogue au moment du design, mais si vous souhaitez contrôler la disposition dynamique au moment de l'exécution, définissez les propriétés de disposition dynamique par programme.  
  
##### Pour définir les propriétés de disposition dynamique par programme  
  
1.  Recherchez ou ajoutez un emplacement dans le code d'implémentation de votre classe de boîte de dialogue où vous souhaitez spécifier la disposition dynamique de la boîte de dialogue.  Par exemple, vous pouvez ajouter la méthode `AdjustLayout` dans votre boîte de dialogue et l'appeler à chaque endroit où la disposition doit être modifiée.  Vous pouvez l'appeler d'abord à partir du constructeur ou après avoir apporté les modifications à la boîte de dialogue.  
  
2.  Pour la boîte de dialogue, appelez [GetDynamicLayout](../Topic/CWnd::GetDynamicLayout.md), une méthode de la classe CWnd.  GetDynamicLayout retourne un pointeur vers un objet CMFCDynamicLayout.  
  
    ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();  
    ```  
  
3.  Pour le premier contrôle à configurer avec un comportement dynamique, utilisez les méthodes statiques sur la classe de disposition dynamique pour créer la structure [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) qui code le type d'ajustement du contrôle.  Pour cela, choisissez d'abord la méthode statique appropriée : [CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md), [CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md), [CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md) ou [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md).  Vous passez ensuite le pourcentage du déplacement horizontal et\/ou du déplacement vertical.  Toutes ces méthodes statiques retournent un nouvel objet MoveSettings que vous pouvez ensuite utiliser pour spécifier le comportement de déplacement d'un contrôle.  
  
     N'oubliez pas que la valeur 100 signifie que le contrôle sera déplacé autant que nécessaire par rapport à la taille modifiée de la boîte de dialogue. L'un des bords du contrôle restera donc à une distance fixe de la nouvelle bordure.  
  
    ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);  
    ```  
  
4.  Procédez de la même façon pour le comportement de redimensionnement, qui utilise le type [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md).  Par exemple, pour spécifier qu'un contrôle ne change pas de taille quand la boîte de dialogue est redimensionnée, utilisez le code suivant :  
  
    ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();  
    ```  
  
5.  Ajoutez le contrôle au gestionnaire de disposition dynamique à l'aide de la méthode [CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md).  Il existe deux surcharges correspondant aux différentes manières de spécifier le contrôle souhaité.  L'une prend le handle de fenêtre \(HWND\) du contrôle et l'autre prend l'ID du contrôle.  
  
    ```  
    dynamicLayout->AddItem(hWndControl, moveSettings, sizeSettings);  
    ```  
  
6.  Répétez l'opération pour chaque contrôle devant être déplacé ou redimensionné.  
  
7.  Si nécessaire, utilisez la méthode [CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md) pour déterminer si un contrôle est déjà dans la liste des contrôles soumis aux modifications de disposition dynamique, ou la méthode [CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md) pour déterminer s'il existe des contrôles qui font l'objet de modifications.  
  
8.  Pour activer la disposition dynamique de la boîte de dialogue, appelez la méthode [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md).  
  
    ```  
    pDialog->EnableDynamicLayout(TRUE);  
    ```  
  
9. Quand un utilisateur redimensionnera la boîte de dialogue, la méthode [CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md) sera appelée, et les paramètres appliqués.  
  
10. Pour désactiver la disposition dynamique, appelez la méthode [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md) avec la valeur `FALSE` pour le paramètre `bEnabled`.  
  
    ```  
    pDialog->EnableDynamicLayout(FALSE);  
    ```  
  
##### Pour définir la disposition dynamique par programme à partir d'un fichier de ressources  
  
1.  Utilisez la méthode [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md) pour spécifier un nom de ressource dans le fichier de script de ressources \(fichier .rc\) où se trouvent les informations de disposition dynamique, comme dans l'exemple suivant :  
  
    ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");  
    ```  
  
     La ressource nommée doit faire référence à une boîte de dialogue contenant des informations de disposition spécifiées sous la forme d'une entrée AFX\_DIALOG\_LAYOUT dans le fichier de ressources, comme dans l'exemple suivant :  
  
    ```  
    /////////////////////////////////////////////////////////////////////////////  
    //  
    // AFX_DIALOG_LAYOUT  
    //  
  
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6400, 0x0028, 0x643c, 0x0028  
    END  
  
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6464, 0x0000, 0x6464, 0x0000, 0x0000, 0x6464, 0x0000, 0x0000  
  
    END  
    ```  
  
## Voir aussi  
 [CMFCDynamicLayout Class](../mfc/reference/cmfcdynamiclayout-class.md)   
 [Classes de contrôle](../mfc/control-classes.md)   
 [Classes de boîte de dialogue](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../mfc/dialog-editor.md)