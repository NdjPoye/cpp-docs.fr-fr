---
title: "Contr&#244;les ActiveX MFC&#160;: ajout d&#39;une page de propri&#233;t&#233;s personnalis&#233;es | Microsoft Docs"
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
  - "contrôles ActiveX (C++), pages de propriétés"
  - "pages de propriétés personnalisées"
  - "contrôles ActiveX MFC (C++), pages de propriétés"
  - "pages de propriétés (C++), contrôles ActiveX MFC"
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: ajout d&#39;une page de propri&#233;t&#233;s personnalis&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Occasionnellement, un contrôle ActiveX a des propriétés qui peuvent raisonnablement tenir sur une page de propriétés.  Dans ce cas, vous pouvez ajouter des pages de propriétés au contrôle ActiveX pour afficher ces propriétés.  
  
 Cet article explique l'ajout de nouvelles pages de propriétés à un contrôle ActiveX qui a déjà au moins une page de propriétés.  Pour plus d'informations sur l'ajout de pages de propriétés \(police, image, ou couleur\), consultez l'article [Contrôles ActiveX MFC : En utilisant les pages de propriétés stock](../mfc/mfc-activex-controls-using-stock-property-pages.md).  
  
 Les procédures suivantes utilisent une infrastructure de contrôle ActiveX d'exemple créée par l'Assistant Contrôle ActiveX.  Par conséquent, les noms de classes et les identificateurs sont uniques dans cet exemple.  
  
 Pour plus d'informations sur l'utilisation des pages de propriétés d'un contrôle ActiveX, consultez les articles suivants :  
  
-   [Contrôles ActiveX MFC : pages de propriétés](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [Contrôles ActiveX MFC : utilisation des pages de propriétés stock](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
    > [!NOTE]
    >  Il est fortement recommandé que les nouvelles pages de propriétés adhèrent à la norme de taille des pages de propriétés du contrôle ActiveX.  Les pages de propriétés d'image et de couleur mesurent 250x62 unités de boîte de dialogue \(DLU\).  La page de propriétés de la police standard est 250x110 DLUs.  La page de propriétés par défaut créée par l'Assistant Contrôle ActiveX utilise la DLU 250x62 standard.  
  
### Pour insérer un modèle de propriétés dans votre projet  
  
1.  Avec votre projet de contrôle ouvert, ouvrez l'affichage des ressources dans l'espace de travail du projet.  
  
2.  Cliquez avec le bouton droit sur Affichage des Ressources pour ouvrir le menu contextuel et cliquez sur **Ajouter une ressource**.  
  
3.  Développez le nœud de **Boîte de dialogue**, puis sélectionnez **IDD\_OLE\_PROPPAGE\_SMALL**.  
  
4.  Cliquez sur `New` pour ajouter l'objet ressource à votre projet.  
  
5.  Sélectionnez le nouveau modèle de la page des propriétés pour actualiser la fenêtre Propriétés.  
  
6.  Entrez une nouvelle valeur pour la propriété **ID**.  Cet exemple utilise **IDD\_PROPPAGE\_NEWPAGE**.  
  
7.  Cliquez sur **Enregistrer** dans la barre d'outils.  
  
### Pour associer le nouveau modèle à une classe  
  
1.  Ouvrez l'Affichage de classes.  
  
2.  Cliquez avec le bouton droit sur Affichage de classes pour ouvrir le menu contextuel.  
  
3.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
     La boîte de dialogue [Ajouter Classe](../ide/add-class-dialog-box.md) s'affiche.  
  
4.  Double\-cliquez sur le modèle de **Classe MFC**.  
  
5.  Dans la zone **Nom de la classe** dans [Assistant Classe MFC](../mfc/reference/mfc-add-class-wizard.md), tapez un nom pour la nouvelle classe de boîte de dialogue. \(Dans cet exemple, `CAddtlPropPage`\)  
  
6.  Si vous souhaitez modifier les noms de fichier,  cliquez sur **Modifier**.  Tapez le nom de votre implémentation et fichiers d'en\-tête, ou acceptez les noms par défaut.  
  
7.  Dans la zone **Classe de base** , sélectionnez `COlePropertyPage`.  
  
8.  Dans la zone de **ID de boîte de dialogue** , sélectionnez **IDD\_PROPPAGE\_NEWPAGE**.  
  
9. Cliquez sur **Terminer** pour créer la classe.  
  
 Pour autoriser l'accès utilisateurs du contrôle à cette nouvelle page de propriétés, apportez les modifications suivantes à la section de macro d'ID de la page de propriétés du contrôle \(trouvée dans le fichier d'implémentation du contrôle\) :  
  
 [!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]  
  
 Notez que vous devez augmenter le deuxième paramètre de la macro `BEGIN_PROPPAGEIDS` \(le nombre de pages de propriétés\) de 1 à 2.  
  
 Vous devez également modifier le fichier d'implémentation du contrôle \(.CPP\) pour ajouter le fichier d'en\-tête \(. H\) de la nouvelle classe de page de propriétés.  
  
 L'étape suivante consiste à créer deux nouvelles ressources de chaîne qui fournissent un nom de type et une légende pour la nouvelle page de propriétés.  
  
#### Pour ajouter de nouvelles ressources de type string à la page de propriétés  
  
1.  À votre projet de contrôle ouvert, ouvrez l'affichage des ressources.  
  
2.  Double\-cliquez sur le dossier **Table de chaînes** puis double\-cliquez sur la ressource existante du tableau de chaînes à laquelle vous souhaitez ajouter une chaîne.  
  
     Cela ouvre la table de chaînes dans une fenêtre.  
  
3.  Sélectionnez la ligne vide à la fin de la table de chaînes et tapez le texte, ou la légende, de la chaîne : par exemple, « page de propriétés supplémentaires. »  
  
     Cela affiche une page **String Properties** qui indique les zones de **Légende** et d'**ID**.  La zone de **Légende** contient la chaîne que vous avez tapée.  
  
4.  Dans la zone d'**ID**, sélectionnez ou tapez un ID pour la chaîne.  Appuyez sur entrée dans lorsque vous avez terminé.  
  
     Cet exemple utilise **IDS\_SAMPLE\_ADDPAGE** pour le nom de la nouvelle page de propriétés.  
  
5.  Répétez les étapes 3 et 4 en utilisant **IDS\_SAMPLE\_ADDPPG\_CAPTION** pour l'ID et « page de propriétés supplémentaires » pour la légende.  
  
6.  Dans le fichier .cpp de votre nouvelle classe de page de propriétés \(dans cet exemple, `CAddtlPropPage`\) modifiez `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` afin que IDS\_SAMPLE\_ADDPAGE soit transmis par [AfxOleRegisterPropertyPageClass](../Topic/AfxOleRegisterPropertyPageClass.md), comme dans l'exemple suivant :  
  
     [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]  
  
7.  Modifiez le constructeur de `CAddtlPropPage` afin que **IDS\_SAMPLE\_ADDPPG\_CAPTION** soit passée au constructeur `COlePropertyPage`, comme suit :  
  
     [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/CPP/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]  
  
 Après avoir effectué à la reconstruction nécessaire, régénérez votre projet et utilisez Container Test pour tester la nouvelle page de propriétés.  Pour plus d'informations sur la manière d'accéder à Test Container, consultez [Test des propriétés et des événements à l'aide de Test Container](../mfc/testing-properties-and-events-with-test-container.md).  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)