---
title: "Contr&#244;les ActiveX MFC&#160;: ajout de propri&#233;t&#233;s stock | Microsoft Docs"
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
  - "BackColor (propriété)"
  - "ForeColor (propriété)"
  - "couleurs de premier plan"
  - "couleurs de premier plan, contrôles ActiveX"
  - "contrôles ActiveX MFC, propriétés"
  - "propriétés (MFC), ajouter stock"
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: ajout de propri&#233;t&#233;s stock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les propriétés de stockage diffèrent des propriétés personnalisées car elles sont déjà implémentée par la classe `COleControl`.  `COleControl` contient les méthodes prédéfinies qui prennent en charge les propriétés communes pour le contrôle.  Certaines propriétés communes incluent la légende du contrôle et les couleurs de premier plan et d'arrière\-plan.  Pour plus d'informations sur d'autres propriétés de stockage, consultez les [Propriétés stockées prises en charge par l'Assistant d'Ajout de Propriétés](#_core_stock_properties_supported_by_classwizard) plus loin dans cet article.  Les entrées de la table de dispatch des propriétés de stockage possèdent toujours le préfixe **DISP\_STOCKPROP**.  
  
 Cet article explique comment ajouter une propriété de stockage \(dans ce cas, la légende\) à un contrôle ActiveX à l'aide de la propriété et explique les modifications résultantes dans le code.  Les rubriques traitées ici sont les suivantes :  
  
-   [À l'aide de l'Assistant d'Ajout de Propriétés pour ajouter une propriété de stockage](#_core_using_classwizard_to_add_a_stock_property)  
  
-   [L'Assistant d'Ajout de Propriétés change pour les propriétés de stockage](#_core_classwizard_changes_for_stock_properties)  
  
-   [Les propriétés de stockage prises en charge par l'Assistant d'Ajout de Propriétés](#_core_stock_properties_supported_by_classwizard)  
  
-   [Propriétés de stockage et notification](#_core_stock_properties_and_notification)  
  
-   [Propriétés de couleur](#_core_color_properties)  
  
    > [!NOTE]
    >  Les contrôles personnalisés Visual Basic possèdent généralement des propriétés telles que en haut, à gauche, largeur, hauteur, sont alignées, balise, nom, TabIndex, tabulation, et parent.  Les conteneurs de contrôle ActiveX, toutefois, sont responsables d'implémenter ces propriétés de contrôle et par conséquent les contrôles ActiveX ne doivent pas prendre en charge ces propriétés.  
  
##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> À l'aide de l'Assistant d'Ajout de Propriétés pour Ajouter une Propriété de Stockage  
 Ajouter des propriétés de stockage requiert moins de code que les propriétés personnalisées d'ajout car la prise en charge de la propriété est gérée automatiquement par `COleControl`.  La procédure suivante montre comment ajouter la propriété de stockage de légende à une infrastructure de contrôle ActiveX et peut également être utilisée pour ajouter d'autres propriétés de stockage.  Remplacez le nom de la propriété de stockage sélectionnée pour la légende.  
  
#### Pour ajouter la propriété de légende à l'aide de l'Assistant d'Ajout de Propriétés  
  
1.  Chargez votre projet de contrôle.  
  
2.  Sous Class View, développez l'arborescence de votre librairie.  
  
3.  Cliquez avec le bouton droit sur le nœud de votre interface pour votre contrôle \(le deuxième nœud de l'arborescence de la librairie\) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
     Cela ouvre l' [Assistant d'Ajout de Propriétés](../ide/names-add-property-wizard.md).  
  
5.  Dans la zone de **Nom de propriété**, cliquez sur **Légende**.  
  
6.  Cliquez sur **Terminer**.  
  
##  <a name="_core_classwizard_changes_for_stock_properties"></a> Les Modifications de l'Assistant d'Ajout de Propriétés pour les Propriétés de Stockage  
 Puisque `COleControl` prend en charge les propriétés de stockage, l'Assistant d'Ajout de Propriétés ne modifie pas la déclaration de classe de quelque manière que ce soit ; elle ajoute une propriété étendue à la table de dispatch.  L'Assistant d'Ajout de Propriétés ajoute la ligne suivante à la table de dispatch de contrôle, qui se trouve dans le fichier d'implémentation \(.CPP\) :  
  
 [!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-properties_1.cpp)]  
  
 La ligne suivante est ajoutée au fichier de description d'interface \(.IDL\) de votre contrôle :  
  
 [!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-properties_2.idl)]  
  
 Cette ligne affecte à la propriété de légende un ID spécifique.  Notez que la propriété est susceptible d'être liée et demandera l'autorisation de la base de données avant de modifier la valeur.  
  
 Cela rend la propriété de légende à la disposition des utilisateurs de votre contrôle.  Pour utiliser la valeur d'une propriété de stockage, accédez à un attribut ou une méthode de la classe de base de `COleControl`.  Pour plus d'informations sur ces attributs et méthodes, consultez la section suivante, propriétés de stockage prises en charge par l'Assistant d'Ajout de Propriétés.  
  
##  <a name="_core_stock_properties_supported_by_classwizard"></a> Les propriétés de stockage prises en charge par l'Assistant d'Ajout de Propriétés  
 La classe de `COleControl` fournit neuf propriétés de stockage.  Vous pouvez ajouter les propriétés souhaitées à l'aide de l'Assistant d'Ajout de Propriétés.  
  
|Propriété|Entrée de dispatch de mappage|Comment accéder à la valeur|  
|---------------|-----------------------------------|---------------------------------|  
|**Apparence**|**DISP\_STOCKPROP\_APPEARANCE\( \)**|Valeur accessible en tant que **m\_sAppearance**.|  
|`BackColor`|**DISP\_STOCKPROP\_BACKCOLOR\( \)**|Valeur accessible en appelant `GetBackColor`.|  
|`BorderStyle`|**DISP\_STOCKPROP\_BORDERSTYLE\( \)**|Valeur accessible en tant que **m\_sBorderStyle**.|  
|**Caption**|**DISP\_STOCKPROP\_CAPTION\( \)**|Valeur accessible en appelant `InternalGetText`.|  
|**Activé**|**DISP\_STOCKPROP\_ENABLED\( \)**|Valeur accessible en tant que **m\_bEnabled**.|  
|**Police**|**DISP\_STOCKPROP\_FONT\( \)**|Consultez l'article [Contrôles ActiveX MFC : Utilisation des polices](../mfc/mfc-activex-controls-using-fonts.md) pour des exemples d'utilisations.|  
|`ForeColor`|**DISP\_STOCKPROP\_FORECOLOR\( \)**|Valeur accessible en appelant `GetForeColor`.|  
|**hWnd**|**DISP\_STOCKPROP\_HWND\( \)**|Valeur accessible en tant que `m_hWnd`.|  
|**Texte**|**DISP\_STOCKPROP\_TEXT\( \)**|Valeur accessible en appelant `InternalGetText`.  Cette propriété équivaut à **Légende**, à l'exception du nom de la propriété.|  
|**ReadyState**|**DISP\_STOCKPROP\_READYSTATE\(\)**|Valeur accessible en tant que m\_lReadyState ou `GetReadyState`|  
  
##  <a name="_core_stock_properties_and_notification"></a> Propriétés de Stockage et Notification  
 La plupart des propriétés de stockage possèdent des fonctions de notification qui peuvent être remplacées.  Par exemple, lorsque la propriété `BackColor` est modifiée, la fonction d' `OnBackColorChanged` \(une méthode de la classe de contrôle\) est appelée.  L'implémentation par défaut \(dans `COleControl`\) appelle `InvalidateControl`.  Remplacez cette fonction si vous souhaitez prendre des mesures supplémentaires en réponse à cette situation.  
  
##  <a name="_core_color_properties"></a> Propriétés de couleur  
 Vous pouvez utiliser les propriétés de stockage `ForeColor` et `BackColor`, ou vos propres propriétés de couleurs personnalisées, lorsque vous peignez le contrôle.  Pour utiliser une propriété de couleur, appelez la méthode [COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md).  Les paramètres de la fonction sont la valeur de la propriété de couleur et un descripteur facultatif de palette.  La valeur de retour est une valeur de **COLORREF** qui peut être passée à des fonctions de GDI, telles que `SetTextColor` et `CreateSolidBrush`.  
  
 Les valeurs de couleur pour `ForeColor` et les propriétés de stockage de `BackColor` sont accessibles en appelant `GetForeColor` ou la fonction `GetBackColor`, respectivement.  
  
 L'exemple suivant illustre l'utilisation de ces deux propriétés de couleurs en peignant un contrôle.  Il initialise une variable temporaire **COLORREF** et un objet `CBrush` avec des appels à `TranslateColor`: l'un utilisant la propriété `ForeColor` et l'autre à l'aide de la propriété `BackColor`.  Un objet temporaire `CBrush` est ensuite utilisé pour peindre le rectangle de contrôle, et la couleur du texte est définie avec la propriété `ForeColor`.  
  
 [!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-properties_3.cpp)]  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : propriétés](../mfc/mfc-activex-controls-properties.md)   
 [Contrôles ActiveX MFC : méthodes](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)