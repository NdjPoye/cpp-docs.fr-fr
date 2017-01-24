---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;une application de ruban &#224; l&#39;aide de MFC | Microsoft Docs"
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
  - "créer une application de ruban (MFC)"
  - "application de ruban, création (MFC)"
ms.assetid: e61393e2-1d6b-4594-a7ce-157d3d1b0d9f
caps.latest.revision: 21
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d&#39;une application de ruban &#224; l&#39;aide de MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas à pas vous montre comment utiliser l'**Assistant Application MFC** pour créer une application comportant un ruban par défaut.  Vous pourrez ensuite développer le ruban en ajoutant une catégorie de ruban **Personnalisée** qui a un volet de ruban **Favoris** et en ajoutant ensuite quelques unes des commandes les plus utilisées au volet.  
  
## Composants requis  
 Cette procédure part du principe que vous avez défini [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour utiliser l'option **Paramètres de développement généraux**.  Si vous utilisez des paramètres différents, certains éléments de l'interface utilisateur qui sont référencés dans les instructions suivantes peuvent ne pas s'afficher.  Pour plus d'informations sur la modification des paramètres, consultez [How to: Reset Your Settings](http://msdn.microsoft.com/fr-fr/c95c51be-e609-4769-abba-65e6beedec76).  
  
### Pour créer une application MFC comportant un ruban  
  
1.  Utilisez l'**Assistant Application MFC** pour créer une application MFC comportant un ruban.  Pour exécuter l'Assistant, dans le menu **Fichier**, pointez sur **Nouveau**, puis cliquez sur **Projet**.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, sous **Modèles installés**, ouvrez le nœud **Visual C\+\+**, sélectionnez **MFC**, puis sélectionnez **Application MFC**.  Tapez un nom de projet, par exemple, `MFCRibbonApp`, puis cliquez sur **OK**.  
  
3.  Sur la première page de l'**Assistant Application MFC**, cliquez sur **Suivant**.  
  
4.  Sur la page **Type d'application**, sous **Style visuel et couleurs**, sélectionnez **Office 2007 \(Thème blue\)**.  Laissez les valeurs des autres paramètres inchangées.  Cliquez sur **Suivant**.  
  
5.  Sur la page **Prise en charge des documents composés**, vérifiez que **Aucun** est sélectionné, puis cliquez sur **Suivant**.  
  
6.  Sur la page **Propriétés du modèle de document**, dans la zone **Extension de fichier**, tapez une extension de nom de fichier pour les documents que cette application crée, par exemple, `mfcrbnapp`.  Cliquez sur **Suivant**.  
  
7.  Sur la page **Prise en charge des bases de données**, vérifiez que **Aucun** est sélectionné, puis cliquez sur **Suivant**.  
  
8.  Sur la page **Fonctionnalités de l'interface utilisateur**, vérifiez que **Utiliser un ruban** est sélectionné.  Cliquez sur **Suivant**.  
  
9. Par défaut, l'**Assistant Application MFC** ajoute la prise en charge de plusieurs volets d'ancrage.  Cette procédure pas à pas ne concernant que le ruban, vous pouvez supprimer ces options de l'application.  Sur la page **Fonctionnalités avancées**, effacez toutes les options.  Cliquez sur **Suivant**.  
  
10. Sur la page **Classes générées**, cliquez sur **Terminer** pour créer l'application MFC.  
  
11. Pour vérifier que l'application a été créée avec succès, générez\-la et exécutez\-la.  Pour générer l'application, dans le menu **Générer**, cliquez sur **Générer la solution**.  Si l'application est générée avec succès, exécutez\-la en cliquant sur **Démarrer le débogage** dans le menu **Déboguer**.  
  
     L'Assistant crée automatiquement un ruban comportant une catégorie de ruban nommée **Accueil**.  Ce ruban contient trois volets de ruban, nommés **Presse\-papiers**, **Vue** et **Fenêtre**.  
  
### Pour ajouter une catégorie et un volet au ruban  
  
1.  Pour ouvrir la ressource de ruban que l'Assistant a créé, dans le menu **Vue**, pointez vers **Autres fenêtres**, puis cliquez sur **Affichage des ressources**.  Dans **Affichage des ressources**, cliquez sur **Ruban**, puis double\-cliquez sur **IDR\_RIBBON**.  
  
2.  Commencez par ajouter une catégorie personnalisée au ruban en double\-cliquant sur **Catégorie** dans la **Boîte à outils**.  
  
     A catégorie comportant la légende **Category1** est créée.  Par défaut, la catégorie contient un seul volet.  
  
     Cliquez avec le bouton droit sur **Category1**, puis cliquez sur **Propriétés**.  Dans la fenêtre **Propriétés**, remplacez la **Légende** par `Personnalisé`.  
  
     Les propriétés **Large images** et **Small Images** spécifient les bitmaps qui sont utilisées comme icônes pour les éléments du ruban dans cette catégorie.  La création de bitmaps personnalisées n'entrant pas dans le cadre de cette procédure, réutilisez les bitmaps créées par l'Assistant.  Les bitmaps de petite taille mesurent 16 pixels par 16 pixels.  Pour les petites images, utilisez les bitmaps qui sont accessibles par l'ID de ressource IDB\_FILESMALL.  Les bitmaps de grande taille mesurent 32 pixels par 32 pixels.  Pour les grandes images, utilisez les bitmaps qui sont accessibles par l'ID de ressource IDB\_FILELARGE.  
  
    > [!NOTE]
    >  Sur les écrans HDPI \(high dots per inch\), les versions HDPI des images sont automatiquement utilisées.  
  
3.  Il vous appartient maintenant de personnaliser le volet.  Les volets sont utilisés pour regrouper des éléments qui sont liés de façon logique les uns aux autres.  Par exemple, sur l'onglet **Accueil** de cette application, les commandes **Couper**, **Copier** et **Coller** se trouvent toutes sur le volet **Presse\-papiers**.  Pour personnaliser le volet, cliquez avec le bouton droit sur **Panel1**, puis cliquez sur **Propriétés**.  Dans la fenêtre **Propriétés**, remplacez la **Légende** par `Favoris`.  
  
     Vous pouvez spécifiez l'**index d'image** du volet.  Ce nombre spécifie l'icône qui est affichée si le volet du ruban est ajouté à la **barre d'outils Accès rapide**.  L'icône n'est pas affichée sur le volet du ruban.  
  
4.  Pour vérifier que le volet et la catégorie de ruban ont été correctement créés, affichez un aperçu du contrôle de ruban.  Dans la **barre d'outils de l'Éditeur Ribbon**, cliquez sur le bouton **Ruban de test**.  Un onglet **Personnalisé** et un volet **Favoris** doivent être affichés sur le ruban.  
  
### Pour ajouter des éléments aux volets de ruban  
  
1.  Pour ajouter des éléments au volet que vous avez créé lors de la procédure précédente, faites glisser les contrôles de la section **Éditeur Ribbon** de la **Boîte à outils** vers le volet dans le mode de conception.  
  
2.  Tout d'abord, ajoutez un bouton **Imprimer**.  Le bouton **Imprimer** comporte un sous\-menu qui contient une commande **Impression Rapide** qui imprime en utilisant l'imprimante par défaut.  Ces deux commandes sont déjà définies pour cette application.  Elles se trouvent dans le menu de l'application.  
  
     Pour créer le bouton **Imprimer**, faites glisser un outil Bouton vers le volet.  
  
     Dans la fenêtre **Propriétés**, remplacez la propriété **ID** par **ID\_FILE\_PRINT**, qui doit déjà être définie.  Remplacez la **Légende** par `Imprimer`.  Modifier **Image Index** en affectant la valeur `4`.  
  
     Pour créer le bouton **Impression Rapide**, cliquez sur la colonne Valeur de propriété en regard de l'option **Éléments de menu**, puis cliquez sur les points de suspension \(**...**\).  Dans l'**Éditeur d'éléments**, cliquez sur le bouton **Ajouter** sans étiquette pour créer un élément de menu.  Dans la fenêtre **Propriétés**, remplacez **Légende** par `Impression Rapide`, **ID** par `ID_FILE_PRINT_DIRECT`, et affectez à **Image** la valeur `5`.  La propriété de l'image spécifie l'icône Impression rapide dans la ressource de bitmap IDB\_FILESMALL.  
  
3.  Pour vérifier que les boutons ont été ajoutés au volet du ruban, générez l'application et exécutez\-la.  Pour générer l'application, dans le menu **Générer**, cliquez sur **Générer la solution**.  Si l'application est générée avec succès, exécutez\-la en cliquant sur le bouton **Démarrer le débogage** dans le menu **Déboguer**.  Le bouton **Imprimer** et la zone de liste déroulante sur le volet **Favoris** de l'onglet **Personnalisé** sur le ruban doivent être affichés.  
  
## Étapes suivantes  
 [Comment : personnaliser la barre d'outils Accès rapide](../mfc/how-to-customize-the-quick-access-toolbar.md)  
  
 [Comment : personnaliser le bouton Application](../mfc/how-to-customize-the-application-button.md)  
  
 Pour consulter des exemples de bout en bout, reportez\-vous à [Exemples \(MFC Feature Pack\)](../top/visual-cpp-samples.md).  
  
## Voir aussi  
 [procédures pas à pas](../mfc/walkthroughs-mfc.md)   
 [Exemples \(MFC Feature Pack\)](../top/visual-cpp-samples.md)