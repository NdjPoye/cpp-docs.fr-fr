---
title: "Contr&#244;les ActiveX MFC&#160;: ajout de propri&#233;t&#233;s personnalis&#233;es | Microsoft Docs"
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
  - "contrôles ActiveX MFC, propriétés"
  - "propriétés (MFC), personnalisé"
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: ajout de propri&#233;t&#233;s personnalis&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les propriétés personnalisées sont différentes des propriétés de stockage dans la mesure où les propriétés personnalisées ne sont pas déjà implémentée par la classe `COleControl`.  Une propriété personnalisée est utilisée pour exposer un certain état ou apparence d'un contrôle ActiveX à un programmeur grâce à son contrôle.  
  
 Cet article explique comment ajouter une propriété personnalisée au contrôle ActiveX à l'aide de l'Assistant Ajout de Propriétés et explique les modifications du code résultantes.  Les rubriques traitées ici sont les suivantes :  
  
-   [Utilisation de l'Assistant d'Ajout de Propriétés pour ajouter une propriété personnalisée](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [L'Assistant Ajout de Propriétés change pour les propriétés personnalisées](#_core_classwizard_changes_for_custom_properties)  
  
 Les propriétés personnalisées se manifestent sous quatre types d'implémentation : variable membre, variable membre avec notification, méthodes Get\/SET, et paramétré.  
  
-   Implémentation d'attribut  
  
     Cette implémentation représente l'état de la propriété comme un attribut dans la classe de contrôle.  Utilisez l'implémentation de variable membre lorsqu'il n'est pas important de savoir quand la valeur de la propriété change.  De ces trois types, cette implémentation crée le moins de code pour la prise en charge de la propriété.  La macro d'entrée du tableau associatif \(map\) de dispatch pour l'implémentation d'attribut est [DISP\_PROPERTY](../Topic/DISP_PROPERTY.md).  
  
-   Attribut avec implémentation de notifications  
  
     Cette implémentation se compose d'un attribut et d'une fonction de notification créée par l'Assistant d'Ajout de Propriétés.  La fonction de notification est appelée automatiquement par le .NET framework lorsque la valeur de la propriété change.  Utilisez l'attribut avec l'implémentation de notification lorsque vous avez besoin d'être informé que la valeur d'une propriété a été changée.  Cette implémentation nécessite plus de temps car elle nécessite un appel de fonction.  La macro d'entrée du tableau associatif \(map\) de dispatch pour cette implémentation est [DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md).  
  
-   Implémentation des méthodes Get\/SET  
  
     Cette implémentation se compose d'une paire de méthodes de la classe de contrôle.  L'implémentation des méthodes Get\/Set appelle automatiquement la fonction membre Get lorsqu'un utilisateur demande la valeur actuelle de la propriété et la fonction membre Set lorsqu'un utilisateur demande à ce que la propriété soit modifiée.  Utilisez cette implémentation lorsque vous devez calculer la valeur d'une propriété au moment de l'exécution, valider une valeur donnée par l'utilisateur avant de modifier la propriété réelle, ou implémenter un type de propriété en lecture \- ou écriture \- seule.  La macro d'entrée du tableau associatif \(map\) de dispatch pour cette implémentation est [DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md).  La section suivante, [Utilisation de l'Assistant Ajout de Propriétés pour ajouter une propriété personnalisée](#_core_using_classwizard_to_add_a_custom_property), utilise la propriété personnalisée CircleOffset pour illustrer cette implémentation.  
  
-   Implémentation paramétrée  
  
     L'implémentation paramétrée est prise en charge par l'Assistant Ajout de Propriétés  Une propriété paramétrée \(parfois appelée tableau de propriétés\) peut être utilisée pour accéder à un ensemble de valeurs via une seule propriété que vous contrôlez.  La macro d'entrée du tableau associatif \(map\) de dispatch pour cette implémentation est `DISP_PROPERTY_PARAM`.  Pour plus d'informations concernant l'implémentation de ce type, consultez [Implémentation d'une propriété paramétrable](../mfc/mfc-activex-controls-advanced-topics.md) dans l'article Contrôles ActiveX: Rubriques avancées.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> Utilisation de l'Assistant Ajout de Propriétés pour ajouter une propriété personnalisée  
 La procédure suivante montre l'ajout d'une propriété personnalisée, CircleOffset, qui utilise l'implémentation des méthodes Get\/Set.  La propriété personnalisée CircleOffset permet à l'utilisateur de décaler le cercle à partir du centre du rectangle englobant.  La procédure pour ajouter des propriétés personnalisées avec une implémentation autre que les méthodes Get\/Set est très similaire.  
  
 Cette procédure peut également être utilisée pour ajouter d'autres propriétés personnalisées que vous souhaitez.  Remplacez le nom de la propriété et les paramètres de CircleOffset par votre nom de propriété personnalisé.  
  
#### Pour ajouter la propriété personnalisée de CircleOffset à l'aide de l'Assistant d'Ajout de Propriétés  
  
1.  Chargez votre projet de contrôle.  
  
2.  Sous Class View, développez l'arborescence de votre librairie.  
  
3.  Cliquez avec le bouton droit sur le nœud de votre interface \(le deuxième nœud de l'arborescence de la librairie\) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
     Cela ouvre l' [Assistant d'Ajout de Propriétés](../ide/names-add-property-wizard.md).  
  
5.  Dans la zone **Nom de la Propriété**, tapez `CircleOffset`.  
  
6.  Dans **Type d'implémentation**, cliquez sur **Méthodes Get\/Set**.  
  
7.  Dans la zone **Type de propriété**, sélectionnez **courte**.  
  
8.  Tapez les noms que vous souhaitez pour les méthodes Get et Set, ou acceptez les noms par défaut.  
  
9. Cliquez sur **Terminer**.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> Modifications dans l'Assistant Ajout de Propriétés pour les propriétés personnalisées  
 Lorsque vous ajoutez la propriété personnalisée CircleOffset, l'Assistant Ajout de Propriétés apporte des modifications à l'en\-tête \(. H\) et aux fichiers \(.CPP\) d'implémentation de la classe de contrôle.  
  
 Les lignes suivantes sont ajoutées au fichier .H pour déclarer deux fonctions appelées `GetCircleOffset` et `SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 La ligne suivante est ajoutée à votre fichier .IDL :  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 Cette ligne affecte un ID spécifique à la propriété CircleOffset, tiré de la position de la méthode dans la liste des méthodes et propriétés de l'Assistant d'Ajout de Propriétés.  
  
 En outre, la ligne suivante est ajoutée à la table de dispatch \(dans le fichier .cpp de la classe de contrôle\) pour mapper la propriété CircleOffset aux deux fonctions du gestionnaire :  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 Enfin, les implémentations des fonctions `GetCircleOffset` et `SetCircleOffset` sont ajoutées à la fin du fichier .cpp.  Dans la plupart des cas, vous modifierez la fonction Get pour retourner la valeur de la propriété.  La fonction Set contiendra généralement du code qui doit être exécuté soit avant soit après que la propriété ne change.  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 Notez que l'Assistant d'Ajout de Propriété ajoute automatiquement un appel à [SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md), au corps de la fonction Set.  L'appel de cette fonction marque le contrôle comme modifié.  Si un contrôle a été modifié, le nouvel état est sauvegardé lorsque le conteneur est enregistré.  Cette fonction doit être appelée chaque fois qu'une propriété, stockée comme une partie de l'état de contrôle permanent, change de valeur.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : propriétés](../mfc/mfc-activex-controls-properties.md)   
 [Contrôles ActiveX MFC : méthodes](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)