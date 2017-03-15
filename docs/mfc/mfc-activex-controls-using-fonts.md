---
title: "Contr&#244;les ActiveX MFC&#160;: utilisation de polices | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnFontChanged"
  - "HeadingFont"
  - "InternalFont"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "polices, contrôles ActiveX"
  - "GetFont (méthode)"
  - "HeadingFont (propriété)"
  - "InternalFont (méthode)"
  - "IPropertyNotifySink (classe)"
  - "contrôles ActiveX MFC, polices"
  - "notifications, polices des contrôles ActiveX MFC"
  - "OnDraw (méthode), contrôles ActiveX MFC"
  - "OnFontChanged (méthode)"
  - "SelectStockFont (méthode)"
  - "SetFont (méthode)"
  - "Stock Font (propriété)"
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Contr&#244;les ActiveX MFC&#160;: utilisation de polices
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si votre contrôle ActiveX affiche du texte, vous pouvez permettre à l'utilisateur du contrôle de modifier l'apparence du texte en modifiant une propriété police.  Les propriétés sont implémentées en tant qu'objets de police et peuvent être de deux types : standard ou personnalisés.  Les propriétés standard sont des propriétés police pré\-implementées que vous ajoutez à l'aide de l'assistant d'ajout de propriété.  Les propriétés personnalisées sont pas pré\-implémentées et le développeur de contrôle détermine le comportement et l'utilisation de la propriété.  
  
 Cet article couvre les rubriques suivantes:  
  
-   [Utilisation de la propriété de police standard](#_core_using_the_stock_font_property)  
  
-   [Utilisation de propriétés personnalisées dans votre contrôle](#_core_implementing_a_custom_font_property)  
  
##  <a name="_core_using_the_stock_font_property"></a> Utilisation de la propriété de police standard  
 Les propriétés standard sont pré\-implémentées par la classe [COleControl](../mfc/reference/colecontrol-class.md).  En outre, une page de propriétés de police standard est également disponible, ce qui permet l'utilisateur de modifier différents attributs de l'objet de police, telles que son nom, sa taille et son style.  
  
 Accédez à l'objet de police par [GetFont](../Topic/COleControl::GetFont.md), [SetFont](../Topic/COleControl::SetFont.md), les fonctions [InternalGetFont](../Topic/COleControl::InternalGetFont.md) de `COleControl`.  L'utilisateur du contrôle accède à l'objet de police via les fonctions `GetFont` et `SetFont` de la même manière que toute autre propriété Get\/Set.  Lorsque l'accès à l'objet de police est requis pour un contrôle, utilisez la fonction `InternalGetFont`.  
  
 Comme l'explique [Contrôles ActiveX MFC : Propriétés](../mfc/mfc-activex-controls-properties.md), ajouter des propriétés standard est simple avec l'[Assistant Ajout de propriété](../ide/names-add-property-wizard.md).  Choisissez la propriété, et l'assistant d'ajout de propriété insère automatiquement l'entrée police standard dans la table de dispatch du contrôle.  
  
#### Pour ajouter la propriété de police standard à l'aide de l'assistant d'ajout de propriété  
  
1.  Chargez votre projet.  
  
2.  Sous Class View, développez l'arborescence de votre librairie.  
  
3.  Cliquez avec le bouton droit sur le nœud de votre interface \(le deuxième nœud de l'arborescence de la librairie\) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
     Cela ouvre l'Assistant Ajout de Propriétés.  
  
5.  Dans la zone de **Nom de propriété**, cliquez sur **Police**.  
  
6.  Cliquez sur **Terminer**.  
  
 L'assistant d'ajout de propriétés ajoute la ligne suivante à la table de dispatch de contrôle, située dans le fichier d'implémentation de la classe de contrôle :  
  
 [!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_1.cpp)]  
  
 En outre, l'asssistant d'ajout de propriété ajoute la ligne suivante au fichier .IDL de contrôle :  
  
 [!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_2.idl)]  
  
 La propriété de légende standard est un exemple d'une propriété de texte qui peut être tracée à l'aide des informations de propriété de police standard.  L'ajout de la propriété de légende standard au contrôle utilise des étapes similaires à celles utilisées pour la propriété de polce standard.  
  
#### Pour ajouter la propriété de légende standard à l'aide de l'assistant d'ajout de propriété  
  
1.  Chargez votre projet.  
  
2.  Sous Class View, développez l'arborescence de votre librairie.  
  
3.  Cliquez avec le bouton droit sur le nœud de votre interface \(le deuxième nœud de l'arborescence de la librairie\) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
     Cela ouvre l'Assistant Ajout de Propriétés.  
  
5.  Dans la zone de **Nom de propriété**, cliquez sur **Légende**.  
  
6.  Cliquez sur **Terminer**.  
  
 L'assistant d'ajout de propriétés ajoute la ligne suivante à la table de dispatch de contrôle, située dans le fichier d'implémentation de la classe de contrôle :  
  
 [!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_3.cpp)]  
  
##  <a name="_core_modifying_the_ondraw_function"></a> Modifier la fonction OnDraw  
 L'implémentation par défaut de `OnDraw` utilise la police système Windows pour tout le texte affiché dans le contrôle.  Cela signifie que vous devez modifier le code `OnDraw` en sélectionnant l'objet police dans le contexte du périphérique.  Pour cela, appelez [COleControl::SelectStockFont](../Topic/COleControl::SelectStockFont.md) et passez le contexte du périphérique du contrôle, comme le montre l'exemple suivant :  
  
 [!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_4.cpp)]  
  
 Après que la fonction `OnDraw` modifiée pour utiliser l'objet de police, tout texte dans le contrôle s'affiche avec les caractéristiques de la propriété de police standard du contrôle.  
  
##  <a name="_core_using_custom_font_properties_in_your_control"></a> Utilisation de propriétés personnalisées dans votre contrôle  
 Outre la propriété de police standard, le contrôle ActiveX peut avoir des propriétés de police personnalisées.  Pour ajouter une propriété de police personnalisée vous devez :  
  
-   Utiliser l'assistand d'ajout de propriété pour implémenter la propriété de police personnalisée.  
  
-   [Traiter les notifications de police](#_core_processing_font_notifications).  
  
-   [Implémenter une interface de notification de nouvelle police](#_core_implementing_a_new_font_notification_interface).  
  
###  <a name="_core_implementing_a_custom_font_property"></a> Implémenter une propriété de police personnalisée  
 Pour implémenter une propriété de police personnalisée, vous utilisez l'assistant d'ajout de propriété pour ajouter la propriété puis effectuez des modifications au code.  Les sections suivantes décrivent comment ajouter la propriété personnalisée `HeadingFont` au contrôle exemple.  
  
##### Pour ajouter la propriété de police personnalisée à l'aide de l'assistant d'ajout de propriété  
  
1.  Chargez votre projet de contrôle.  
  
2.  Sous Class View, développez l'arborescence de votre librairie.  
  
3.  Cliquez avec le bouton droit sur le nœud de votre interface \(le deuxième nœud de l'arborescence de la librairie\) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
     Cela ouvre l'Assistant Ajout de Propriétés.  
  
5.  Dans la zone **Nom de la propriété**, tapez un nom pour votre propriété.  Pour cet exemple, utilisez **HeadingFont**.  
  
6.  Dans **Type d'implémentation**, cliquez sur **Méthodes Get\/Set**.  
  
7.  Dans la zone de **Type de propriété**, sélectionnez **IDispatch\*** pour le type de propriété.  
  
8.  Cliquez sur **Terminer**.  
  
 L'assistant d'ajout de propriété crée le code pour ajouter la propriété personnalisée `HeadingFont` à la classe `CSampleCtrl` et au fichier SAMPLE.IDL.  Comme `HeadingFont` une propriété de type Get\/Set, l'assistant d'ajout de propriété modifie la table de dispatch de la classe `CSampleCtrl` pour inclure une macro entrée `DISP_PROPERTY_EX_ID`[DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md) :  
  
 [!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_5.cpp)]  
  
 La macro `DISP_PROPERTY_EX` associe le nom de la propriété `HeadingFont` avec les méthodes Get\/Set correspondantes de la classe `CSampleCtrl`, `GetHeadingFont` et `SetHeadingFont`.  Le type de la valeur de propriété est également spécifié ; dans ce cas, **VT\_FONT**.  
  
 L'assistant d'ajout de propriété ajoute également une déclaration dans le fichier d'en\-tête de contrôle \(.H\) pour que les fonctions `GetHeadingFont` et `SetHeadingFont` s'exécutent et ajoutent leurs modèles de fonctions au fichier d'implémentation du contrôle \(.CPP\) :  
  
 [!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_6.cpp)]  
  
 Enfin, l'assistant d'ajout de propriété modifie le fichier .IDL de contrôleen ajoutant une entrée pour la propriété `HeadingFont` :  
  
 [!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_7.idl)]  
  
### Modificatons au code du contrôle  
 Maintenant que vous avez ajouté la propriété `HeadingFont` au contrôle, vous devez apporter certaines modifications à l'en\-tête et aux fichiers d'implémentation du contrôle pour supporter pleinement la nouvelle propriété.  
  
 Dans le fichier d'en\-tête de contrôle \(.H\), déclarez une variable membre protégée comme suit :  
  
 [!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_8.h)]  
  
 Dans le fichier d'implémentation du contrôle \(.CPP\), procédez comme suit :  
  
-   Initialisez `m_fontHeading` dans le constructeur de contrôle.  
  
     [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_9.cpp)]  
  
-   Déclarez une structure statique **FONTDESC** contenant les attributs par défaut de la police.  
  
     [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_10.cpp)]  
  
-   Dans la fonction membre de contrôle `DoPropExchange`, ajoutez un appel à la fonction `PX_Font`.  Cela fournit l'initialisation et la persistance de votre propriété personnalisée de police.  
  
     [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_11.cpp)]  
  
-   Terminez l'implémentation de la fonction membre `GetHeadingFont` du contrôle.  
  
     [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_12.cpp)]  
  
-   Terminez l'implémentation de la fonction membre `SetHeadingFont` du contrôle.  
  
     [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_13.cpp)]  
  
-   Modifiez la fonction membre `OnDraw` contrôle pour définir une variable pour contenir la police sélectionnée précédemment.  
  
     [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_14.cpp)]  
  
-   Modifiez la fonction membre `OnDraw` du contrôle pour sélectionner les polices dans le contexte de périphérique en ajoutant la ligne suivante où la police doit être utilisée.  
  
     [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_15.cpp)]  
  
-   Modifiez la fonction membre `OnDraw` du contrôle pour sélectionner la police précédente à nouveau dans le contexte de périphérique en ajoutant la ligne suivante après que la police a été utilisée.  
  
     [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_16.cpp)]  
  
 Lorsque la propriété personnalisée a été implémentée, la page de propriétés de la police standard devrait être implémentée, ce qui permet aux utilisateurs de contrôle de modifier la police actuelle du contrôle.  Pour ajouter l'ID de propriétés à la page de propriétés de la police standard, insérez la ligne suivante après la macro `BEGIN_PROPPAGEIDS` :  
  
 [!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_17.cpp)]  
  
 Vous devez également incrémenter de 1 le compte de paramètre de la macro `BEGIN_PROPPAGEIDS`.  La ligne suivante illustre ce comportement :  
  
 [!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_18.cpp)]  
  
 Une fois que ces modifications ont été apportées, recréez le projet complet pour intégrer des fonctionnalités supplémentaires.  
  
###  <a name="_core_processing_font_notifications"></a> Traiter les notifications de police.  
 Dans la plupart des cas le contrpole a besoin de savoir quand les caractéristiques de la police ont été modifiées.  Chaque objet de police peut fournir des notifications lorsqu'il est modifié en appelant une fonction membre de l'interface **IFontNotification**, implémenté par `COleControl`.  
  
 Si le contrôle utilise la propriété de police standard, les notifications sont gérées par la fonction membre `OnFontChanged` de `COleControl`.  Lorsque vous ajoutez des propriétés de police personnalisées, vous pouvez les faire utiliser la même implémentation.  Dans l'exemple de la section précédente, cela était possible en passant &**m\_xFontNotification** lors de l'initialisation de la variable membre **m\_fontHeading**.  
  
 ![Implémentation de plusieurs interfaces d'objet Font](../mfc/media/vc373q1.png "vc373Q1")  
Implémentation d'interfaces d'objet de police mutlitples  
  
 Les lignes pleines dans l'illustration ci\-dessus indiquent que les deux objets de police utilisent la même implémentation de **IFontNotification**.  Cela peut poser des problèmes si vous souhaitez distinguées les polices modifiées.  
  
 Une méthode pour distinguer les notifications de police du contrôle consiste à créer une implémentation distincte de l'interface **IFontNotification** pour chaque objet de police dans le contrôle.  Cette technique vous permet d'optimiser votre code de dessin en mettant à jour uniquement la chaîne, ou les chaînes, qui utilisent la police récemment modifiée.  Les sections suivantes présentent les étapes nécessaires pour implémenter les interfaces distinctes de notification d'une seconde propriété de police.  Il est supposé que la seconde propriété de police est la propriété `HeadingFont` ajoutée dans la section précédente.  
  
###  <a name="_core_implementing_a_new_font_notification_interface"></a> Implémenter une interface de notification de nouvelle police.  
 Pour distinguer les notifications de deux ou plusieurs polices, une nouvelle interface de notification doit être implémentée pour chaque police utilisée dans le contrôle.  Les sections suivantes décrivent comment implémenter une interface de notification de nouvelle police en modifiant l'en\-tête et les fichiers d'implémentation du contrôle.  
  
### Ajouts au fichier d'en\-tête  
 Dans le fichier d'en\-tête du contrôle \(.H\), ajoutez les lignes suivantes à la déclaration de classe :  
  
 [!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_19.h)]  
  
 Cela crée une implémentation de l'interface `IPropertyNotifySink` appelée `HeadingFontNotify`.  Cette nouvelle interface contient une méthode appelée `OnChanged`.  
  
### Ajouts au fichier d'implémentation  
 Dans le code qui initialise la police du titre \(dans le constructeur de contrôle\), changez `&m_xFontNotification` en `&m_xHeadingFontNotify`.  Puis ajoutez le code suivant :  
  
 [!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/CPP/mfc-activex-controls-using-fonts_20.cpp)]  
  
 Les méthodes `AddRef` et `Release` dans l'interface `IPropertyNotifySink` contiennent le nombre de référence pour l'objet de contrôle ActiveX.  Lorsque le contrôle obtient l'accès au pointeur d'interface, le contrôle appelle `AddRef` pour incrémenter le nombre de références.  Lorsque le contrôle a terminé avec le pointeur, il appelle `Release`, d'une façon similaire à l'appel à **GlobalFree** pour libérer un bloc de mémoire globale.  Lorsque le nombre de références de l'interface parvient à zéro, l'implémentation de l'interface peut être libérée.  Dans cet exemple, la fonction `QueryInterface` retourne un pointeur vers une interface `IPropertyNotifySink` sur un objet particulier.  Cette fonction permet à un contrôle ActiveX d'interroger un objet pour déterminer les interfaces qu'elle prend en charge.  
  
 Une fois ces modifications apportées à votre projet, reconstruisez le projet et utilisez Container Test pour tester l'interface.  Pour plus d'informations sur la manière d'accéder à Test Container, consultez [Test des propriétés et des événements à l'aide de Test Container](../mfc/testing-properties-and-events-with-test-container.md).  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : utilisation d'images dans un contrôle ActiveX](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)   
 [Contrôles ActiveX MFC : utilisation des pages de propriétés stock](../mfc/mfc-activex-controls-using-stock-property-pages.md)