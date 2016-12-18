---
title: "Contr&#244;les ActiveX MFC&#160;: pages de propri&#233;t&#233;s | Microsoft Docs"
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
  - "CPropertyPageDialog (classe)"
  - "DDP_ (fonctions)"
  - "DoDataExchange (méthode)"
  - "contrôles ActiveX MFC, propriétés"
  - "contrôles ActiveX MFC, pages de propriétés"
  - "OLEIVERB_PROPERTIES"
  - "pages de propriétés, contrôles ActiveX MFC"
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: pages de propri&#233;t&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les pages de propriétés permettent à l'utilisateur d'un contrôle ActiveX d'afficher et de modifier ses propriétés.  Ces propriétés sont accessibles en appelant une boîte de dialogue des propriétés du contrôle, qui contient une ou plusieurs pages de propriétés constituant une interface graphique personnalisée pour afficher et modifier les propriétés du contrôle.  
  
 Les pages de propriétés du contrôle ActiveX sont affichées de deux façons :  
  
-   Lorsque le verbe des propriétés du contrôle \(**OLEIVERB\_PROPERTIES**\) est appelé, le contrôle ouvre une boîte de dialogue modale de propriétés qui contient les pages de propriétés du contrôle.  
  
-   Le conteneur peut afficher sa propre boîte de dialogue non modale qui indique les pages de propriétés du contrôle sélectionné.  
  
 La boîte de dialogue \(illustrée dans la figure ci\-dessous\) est constituée d'une zone pour afficher la page des propriétés actuelles, les onglets pour basculer entre les pages de propriétés, ainsi qu'une collection de boutons qui effectuent des tâches courantes telles que fermer la boîte de dialogue de propriétés, l'annulation de toutes les modifications apportées, ou appliquer immédiatement toutes les modifications apportées au contrôle ActiveX.  
  
 ![Boîte de dialogue Propriétés pour Circ3](../mfc/media/vc373i1.png "vc373I1")  
Boîte de dialogue Propriétés  
  
 Cet article traite des rubriques relatives à l'utilisation des pages de propriétés d'un contrôle ActiveX.  Ces niveaux sont les suivants :  
  
-   [Implémenter la page de propriétés par défaut d'un contrôle ActiveX](#_core_implementing_the_default_property_page)  
  
-   [Ajout de contrôles à une feuille de propriétés](#_core_adding_controls_to_a_property_page)  
  
-   [Personnaliser la fonction de DoDataExchange](#_core_customizing_the_dodataexchange_function)  
  
 Pour plus d'informations sur l'utilisation des pages de propriétés d'un contrôle ActiveX, consultez les articles suivants :  
  
-   [Contrôles ActiveX MFC : ajout d'une page de propriétés personnalisées](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
-   [Contrôles ActiveX MFC : utilisation des pages de propriétés stock](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
 Pour plus d'informations sur l'utilisation des feuilles de propriétés dans une application de MFC autre qu'un contrôle ActiveX, consultez [Feuilles de propriétés](../mfc/property-sheets-mfc.md).  
  
##  <a name="_core_implementing_the_default_property_page"></a> Implémenter la page de propriétés par défaut  
 Si vous utilisez l'Assistant Contrôle ActiveX pour créer le projet de contrôle, l'Assistant Contrôle ActiveX fournit une classe par défaut pour la page des propriétés pour le contrôle dérivée de [COlePropertyPage Class](../mfc/reference/colepropertypage-class.md).  Initialement, cette page de propriétés est vide, mais vous pouvez ajouter un contrôle de la boîte de dialogue ou un ensemble de contrôles à celui\-ci.  Comme l'Assistant Contrôle ActiveX crée uniquement une classe page de propriétés par défaut, les classes supplémentaires de la page de propriétés \(également dérivées de `COlePropertyPage`\) doivent être créées à l'aide de l'Affichage de classes.  Pour plus d'informations sur cette procédure, consultez [Contrôles ActiveX MFC : ajout d'une page de propriétés personnalisées](../mfc/mfc-activex-controls-adding-another-custom-property-page.md).  
  
 Implémenter une page de propriétés \(dans ce cas, la valeur par défaut\) est un processus en trois étapes :  
  
#### Pour implémenter une page de propriétés  
  
1.  Ajoutez une classe dérivée de `COlePropertyPage` au projet de contrôle.  Si le projet a été créé à l'aide de l'Assistant Contrôle ActiveX \(comme dans ce cas\), la classe par défaut de la page de propriétés existe déjà.  
  
2.  Utilisez l'éditeur de boîtes de dialogue pour ajouter tous les contrôles de page de propriétés.  
  
3.  Personnalisez la fonction `DoDataExchange` de la classe dérivée de `COlePropertyPage` pour échanger des valeurs entre le contrôle de page de propriétés et le contrôle ActiveX.  
  
 À titre de exemple, les procédures suivantes utilisent une vérification simple \(nommée « exemple »\).  Cet exemple a été créé à l'aide de l'Assistant Contrôle ActiveX et contient uniquement la propriété de légende de titre.  
  
##  <a name="_core_adding_controls_to_a_property_page"></a> Ajout de contrôles à une feuille de propriétés  
  
#### Pour ajouter des contrôles dans une page de propriétés  
  
1.  À votre projet de contrôle ouvert, ouvrez l'affichage des ressources.  
  
2.  Double\-cliquez sur l'icône de répertoire de la **Boîte de dialogue**.  
  
3.  Ouvrez la boîte de dialogue **IDD\_PROPPAGE\_SAMPLE** .  
  
     Assistant Contrôle ActiveX ajoute le nom du projet à la fin de l'ID de la boîte de dialogue, dans ce cas, Exemple.  
  
4.  Faites glisser le contrôle sélectionné de la boîte à outils vers la zone de la boîte de dialogue.  
  
5.  Pour cet exemple, un contrôle d'étiquette de texte « Légende : » et un contrôle de zone d'édition avec un identificateur **IDC\_CAPTION** sont suffisants.  
  
6.  Cliquez sur **Enregistrer** sur la barre d'outils pour enregistrer vos modifications.  
  
 Maintenant que l'interface utilisateur a changé, vous devez lier la zone d'édition à la propriété de légende.  Cette opération s'effectue dans la section suivante en modifiant la fonction `CSamplePropPage::DoDataExchange`.  
  
##  <a name="_core_customizing_the_dodataexchange_function"></a> Personnaliser la fonction de DoDataExchange  
 La fonction [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md) de votre page de propriétés permet aux valeurs de propriétés d'être liées avec les valeurs réelles des propriétés du contrôle.  Pour créer des liens, vous devez mapper les champs appropriés de propriétés à leurs propriétés du contrôle respectives.  
  
 Ces mappages sont implémentés en utilisant les fonctions de **DDP\_** de la page de propriétés.  Les fonctions **DDP\_** fonctionnent comme les fonctions **DDX\_** utilisées dans les boîtes de dialogue standard de MFC, à une exception.  Outre la référence à une variable membre, les fonctions de **DDP\_** prennent le nom de la propriété de contrôle.  Voici une entrée standard de la fonction `DoDataExchange` pour une page de propriétés.  
  
 [!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/CPP/mfc-activex-controls-property-pages_1.cpp)]  
  
 Cette fonction associe la variable membre `m_caption` de la page de propriétés à la légende, à l'aide de la fonction `DDP_TEXT`.  
  
 Lorsque vous faites insérer le contrôle de page de propriétés, vous devez établir un lien entre le contrôle de page de propriétés, `IDC_CAPTION`, et la propriété de contrôle réelle, légende, la fonction de **DDP\_Text** comme décrit ci\-dessus.  
  
 [Pages de propriétés](../mfc/reference/property-pages-mfc.md) sont disponibles pour d'autres types de contrôle de la boîte de dialogue, tels que les cases à cocher, les cases d'option, les zones de liste.  Le tableau ci\-dessous répertorie l'ensemble des fonctions **DDP\_** de propriétés et leurs objectifs :  
  
### Fonctions de page de propriétés  
  
|Nom de la fonction|Utilisez cette fonction pour lier|  
|------------------------|---------------------------------------|  
|`DDP_CBIndex`|L'index de la chaîne sélectionnée dans la zone de liste déroulante avec une propriété de contrôle.|  
|`DDP_CBString`|L'index de la chaîne sélectionnée dans la zone de liste modifiable avec une propriété de contrôle.  La chaîne sélectionnée peut démarrer avec les mêmes lettres que la valeur de la propriété mais n'a pas besoin d'une correspondance totale.|  
|`DDP_CBStringExact`|L'index de la chaîne sélectionnée dans la zone de liste modifiable avec une propriété de contrôle.  La chaîne sélectionnée et la valeur de chaîne de la propriété doivent correspondre exactement.|  
|`DDP_Check`|La case à cocher avec une propriété de contrôle.|  
|`DDP_LBIndex`|L'index de la chaîne sélectionnée dans la zone de liste avec une propriété de contrôle.|  
|`DDP_LBString`|L'index de la chaîne sélectionnée dans la zone de liste avec une propriété de contrôle.  La chaîne sélectionnée peut démarrer avec les mêmes lettres que la valeur de la propriété mais n'a pas besoin d'une correspondance totale.|  
|`DDP_LBStringExact`|L'index de la chaîne sélectionnée dans la zone de liste avec une propriété de contrôle.  La chaîne sélectionnée et la valeur de chaîne de la propriété doivent correspondre exactement.|  
|`DDP_Radio`|Une case d'option avec une propriété de contrôle.|  
|**DDP\_Text**|Texte avec une propriété de contrôle.|  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [COlePropertyPage Class](../mfc/reference/colepropertypage-class.md)