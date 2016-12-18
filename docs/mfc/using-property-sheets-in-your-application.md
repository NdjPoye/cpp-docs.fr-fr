---
title: "Utilisation des feuilles de propri&#233;t&#233;s dans votre application | Microsoft Docs"
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
  - "AddPage (méthode)"
  - "CPropertyPage (classe), styles"
  - "Create (méthode) (C++), feuilles de propriétés"
  - "ressources de boîte de dialogue"
  - "modèles de boîte de dialogue, feuilles de propriétés"
  - "DoModal (méthode) (feuilles de propriétés)"
  - "pages de propriétés, feuilles de propriétés"
  - "feuilles de propriétés, à propos des feuilles de propriétés"
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des feuilles de propri&#233;t&#233;s dans votre application
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour utiliser une feuille de propriétés dans votre application, procédez comme suit :  
  
1.  Créez une ressource modèle de la boîte de dialogue dans chaque page de propriétés.  N'oubliez pas que l'utilisateur peut basculer d'une page à l'autre, donc la présentation de chaque page doit être aussi cohérente que possible.  
  
     Les modèles de la boîte de dialogue pour toutes les pages ne doivent pas nécessairement avoir la même taille.  L'infrastructure utilise la taille de la plus grande page pour déterminer la quantité d'espace à allouer dans la feuille de propriétés pour les pages de propriétés.  
  
     Lorsque vous créez la ressource modèle de la boîte de dialogue pour une page de propriétés, vous devez spécifier les styles suivants dans la feuille de propriétés de Propriétés De Dialogue:  
  
    -   Définissez la zone d'édition de **Légende** dans la page de **Général** le texte que vous souhaitez voir s'afficher dans l'onglet de cette page.  
  
    -   Définissez la zone de liste de **Style** dans la page de **Styles** à **Enfant**.  
  
    -   Définissez la zone de liste de **Bordure** dans la page de **Styles** à **Fine**.  
  
    -   Vérifiez que la case à cocher de **Barre de Titre** dans la page de **Styles** est sélectionnée.  
  
    -   Vérifiez que la case à cocher de **Desactivé** dans la page de **Plus de Styles** est sélectionnée.  
  
2.  Créez une [CPropertyPage](../mfc/reference/cpropertypage-class.md)\- classe dérivée correspondant à chaque modèle de page de propriétés.  Voir [Ajouter une classe](../ide/adding-a-class-visual-cpp.md).  Choisissez `CPropertyPage` en tant que classe de base.  
  
3.  Créez des variables membres pour contenir les valeurs de cette page de propriétés.  Le processus d'ajout des variables membres à une page de propriétés est identique au processus d'ajout des variables membres à une boîte de dialogue, car une page de propriétés est une boîte de dialogue spécialisée.  Pour plus d'informations, consultez [Définir les variables membres pour les contrôles de la boîte de dialogue](../mfc/defining-member-variables-for-dialog-controls.md).  
  
4.  Construisez un objet d' [CPropertySheet](../mfc/reference/cpropertysheet-class.md) dans votre code source.  Généralement, vous construisez l'objet d' `CPropertySheet` dans le gestionnaire de la commande qui affiche la feuille de propriétés.  Cet objet représente la feuille de propriétés entière.  Si vous créez une feuille de propriétés modale avec la fonction de [DoModal](../Topic/CPropertySheet::DoModal.md), l'infrastructure fournit trois boutons de commande par défaut : OK, Annuler et Appliquer.  L'infrastructure ne crée pas de boutons de commande pour les feuilles de propriétés non modales créées avec la fonction d' [Créer](../Topic/CPropertySheet::Create.md).  Vous n'avez pas besoin de dériver une classe d' `CPropertySheet` à moins de vouloir ajouter d'autres contrôles \(comme une fenêtre d'aperçu\) ou afficher une feuille de propriétés non modales.  Cette étape est nécessaire pour les feuilles de propriétés non modales car elles ne contiennent aucun contrôle par défaut qui peut être utilisé pour fermer la feuille de propriétés.  
  
5.  Pour chaque page à ajouter à la feuille de propriétés, procédez comme suit :  
  
    -   Construisez un objet pour chaque `CPropertyPage`\- classe dérivée que vous avez créée précédemment pendant ce processus.  
  
    -   Appelez [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) pour chaque page.  
  
     En général, l'objet qui crée `CPropertySheet` crée également les objets d' `CPropertyPage` de cette étape.  Toutefois, si vous implémentez une `CPropertySheet`\- classe dérivée, vous pouvez inclure des objets d' `CPropertyPage` dans l'objet d' `CPropertySheet` et appeler `AddPage` pour chaque page d' `CPropertySheet`\- constructeur dérivé de la classe.  `AddPage` ajoute l'objet d' `CPropertyPage` à la liste de pages de la feuille de propriétés mais ne crée pas réellement la fenêtre de cette page.  Par conséquent, il n'est pas nécessaire d'attendre jusqu'à la conception de la fenêtre de feuille de propriétés pour appeler `AddPage`; vous pouvez appeler `AddPage` du constructeur de la feuille de propriétés.  
  
     Par défaut, si une feuille de propriétés contient plus d'onglets que ceux qui tiennent sur une ligne de la feuille de propriétés, les onglets s'empileront sur plusieurs lignes.  Pour désactiver l'empilement, appelez [CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md) avec le paramètre réglé à **FALSE**.  Vous devez appeler `EnableStackedTabs` lorsque vous créez la feuille de propriétés.  
  
6.  Appelez [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) ou [Créer](../Topic/CPropertySheet::Create.md) pour afficher la feuille de propriétés.  Appelez `DoModal` pour créer une feuille de propriétés comme une boîte de dialogue modale.  Appelez **Créer** pour créer une feuille de propriétés comme boîte de dialogue non modale.  
  
7.  Echangez des données entre les pages de propriétés et le propriétaire de la feuille de propriétés.  Ceci est expliqué dans l'article [Échange de données](../mfc/exchanging-data.md).  
  
 Pour obtenir un exemple de l'utilisation des feuilles de propriétés, consultez l'exemple général de MFC [PROPDLG](../top/visual-cpp-samples.md).  
  
## Voir aussi  
 [Feuilles de propriétés](../mfc/property-sheets-mfc.md)