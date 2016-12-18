---
title: "Architecture de la page de d&#233;marrage | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "architecture de la page de démarrage"
  - "xaml de page de démarrage"
ms.assetid: f94afe27-0be3-47d9-8e17-b0fd429017bd
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# Architecture de la page de d&#233;marrage
Ce document décrit l'architecture de la fenêtre Outil de la page de démarrage qui est incluse dans Visual Studio.  Vous pouvez utiliser ces informations pour ajouter ou modifier des éléments sur la page de démarrage sans modifier sa structure sous\-jacente.  
  
 La page de démarrage Visual Studio est écrite en langage \(WPF\) XAML \(extensible application markup Windows Presentation Foundation \(XAML\).  Pour plus d'informations sur le balisage XAML, consultez [Vue d'ensemble du langage XAML \(WPF\)](../Topic/XAML%20Overview%20\(WPF\).md).  
  
## structure de page  
 La page de démarrage se compose d'un élément d' <xref:System.Windows.Controls.Image> et de deux éléments d' <xref:System.Windows.Controls.Grid> dans un élément d' `Grid`de niveau supérieur.  l'élément d' `Image` couvre le haut de la fenêtre Outil et contient le logo de Visual Studio.  Sous le logo, l'élément d' `Grid`de gauche contient les boutons de commande pour les nouveaux projets, la liste de **Projets récents** , et une zone pour les options de la page de démarrage.  L'élément d' `Grid`de droite contient un élément d' <xref:System.Windows.Controls.TabControl> qui possède un onglet de **Démarrer** , un onglet d' **aide et ressources** , et un onglet de **Nouveautés** .  Une colonne centrale est définie entre les éléments gauche et droit d' `Grid`, mais elle n'a aucun contenu et est utilisée uniquement comme écartement.  
  
### corps de fenêtre  
 l'arrière\-plan de la fenêtre Outil est représenté par l'élément de niveau supérieur d' `Grid`.  Les largeurs des colonnes clés sont définies ici, dans l'élément d' `ColumnDefinitions` .  La hauteur de l'image de logo est définie dans l'élément d' `RowDefinitions` .  
  
 Ligne des définitions et des définitions de colonne sont stockées dans des tableaux de base zéro.  Pour positionner un élément dans une grille, définissez les attributs d' `Grid.Column` et d' `Grid.Row` pour faire correspondre les index d' <xref:System.Windows.Controls.ColumnDefinition> et des éléments de travail <xref:System.Windows.Controls.RowDefinition> .  
  
### image de logo  
 Le logo Visual Studio occupe la ligne du haut de la grille de niveau supérieur \(`Grid.Row="0"`\) en tant qu'élément d' `Image` .  Pour afficher une autre image, indiquez l'attribut d' `Source` de l'élément d' `Image` un fichier image différent.  Pour supprimer l'image, supprimez l'élément d' `Image` et affectez à l'attribut d' `height` de l'élément de niveau supérieur correspondant d' `RowDefinition` à `0` \(zéro\) pour masquer la ligne du haut de la grille.  
  
### colonne de gauche  
 La colonne de gauche de la page de démarrage est représentée par un élément d' `Grid`à l'adresse `Grid.Column="0"` et `Grid.Row="1"`.  Cet élément contient des définitions de trois lignes, qui hébergent la grille de boutons de commande, la grille récente de projets, et un élément d' `StackPanel` pour afficher les options de Visual Studio.  
  
 Vous pouvez ajouter un élément à la grille en l'ajoutant à l'une des lignes existantes ou en ajoutant une nouvelle définition de ligne.  Lorsque vous définissez une nouvelle ligne, n'oubliez pas d'incrémenter les valeurs d' `Grid.Row` de tous les éléments qui apparaissent sous la nouvelle ligne.  
  
### Colonne centrale  
 La colonne centrale est une écartement et ne contient pas d'éléments.  Pour ajouter un élément à la colonne centrale, placez \-la à l'adresse `Grid.Column="1"` et `Grid.Row="1"`.  Veillez à ajuster l'attribut d' `Width` de la définition de colonne pour recevoir la modification.  
  
### colonne de droite  
 La colonne de droite contient un élément d' `Grid` à l'adresse `Grid.Column="1"` et `Grid.Row="1"`.  la grille contient un élément d' `TabControl` qui a trois onglets.  
  
 Vous pouvez ajouter un onglet en ajoutant un élément d' <xref:System.Windows.Controls.TabItem> au contrôle onglet, comme indiqué dans [Procédure pas à pas : Ajout de code XAML personnalisé à la Page de démarrage](../Topic/Walkthrough:%20Adding%20Custom%20XAML%20to%20the%20Start%20Page.md), ou vous pouvez modifier ou supprimer des onglets existants.  Les Onglets apparaissent de gauche à droite dans l' \(UI\)interface utilisateur dans le même ordre que leur apparition de haut en bas dans le balisage.  
  
 Si vous ajoutez un élément à la grille de la colonne de droite en dehors de le contrôle onglet, nous vous conseillons de définir une nouvelle ligne ou colonne dans la grille pour garantir qu'elle apparaît comme prévu.  
  
## Voir aussi  
 [Personnalisation de la page de démarrage](../Topic/Customizing%20the%20Start%20Page%20for%20Visual%20Studio.md)   
 [Bonnes pratiques pour la page de démarrage](../misc/start-page-best-practices.md)   
 [Déploiement de Pages de démarrage personnalisées](../Topic/Deploying%20Custom%20Start%20Pages.md)