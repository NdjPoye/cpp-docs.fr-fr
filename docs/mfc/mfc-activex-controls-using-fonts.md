---
title: 'Contrôles ActiveX MFC : Utilisation de polices | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b53ab98e44a8696795e810b8d6f643720d8f9655
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-using-fonts"></a>Contrôles ActiveX MFC : utilisation des polices
Si votre contrôle ActiveX affiche du texte, vous pouvez autoriser l’utilisateur du contrôle modifier l’apparence du texte en modifiant une propriété de police. Propriétés de police sont implémentées en tant qu’objets de police et peut prendre l’une des deux types : stock ou personnalisée. Propriétés stock Font sont des propriétés de polices préimplémentées que vous pouvez ajouter à l’aide de l’Assistant Ajout de propriété. Les propriétés de police personnalisées ne sont pas préimplémentées et le développeur contrôle détermine le comportement et l’utilisation de la propriété.  
  
 Cet article couvre les rubriques suivantes :  
  
-   [À l’aide de la propriété Stock Font](#_core_using_the_stock_font_property)  
  
-   [À l’aide des propriétés de la police personnalisée dans votre contrôle](#_core_implementing_a_custom_font_property)  
  
##  <a name="_core_using_the_stock_font_property"></a> À l’aide de la propriété Stock Font  
 Propriétés stock Font sont préimplémentées par la classe [COleControl](../mfc/reference/colecontrol-class.md). En outre, une page de propriétés de police standard est également disponible, permettant à l’utilisateur de modifier divers attributs de l’objet de police, telles que son nom, la taille et le style.  
  
 Accéder à l’objet de police via le [GetFont](../mfc/reference/colecontrol-class.md#getfont), [SetFont](../mfc/reference/colecontrol-class.md#setfont), et [InternalGetFont](../mfc/reference/colecontrol-class.md#internalgetfont) fonctions de `COleControl`. L’utilisateur du contrôle accédera à l’objet de police via le `GetFont` et `SetFont` les fonctions de la même manière que n’importe quelle autre propriété Get/Set. Lors de l’accès à l’objet de police est requis à partir d’un contrôle, utilisez la `InternalGetFont` (fonction).  
  
 Comme indiqué dans [contrôles ActiveX MFC : propriétés](../mfc/mfc-activex-controls-properties.md), ajout de propriétés stock est facile avec la [Assistant Ajout de propriété](../ide/names-add-property-wizard.md). Vous choisissez la propriété de police, et l’Assistant Ajout de propriété insère automatiquement l’entrée stock Font dans la table de dispatch du contrôle.  
  
#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>Pour ajouter la propriété stock Font à l’aide de l’Assistant Ajout de propriété  
  
1.  Chargez votre projet de contrôle.  
  
2.  Dans l’Affichage de classes, développez le nœud Bibliothèque de votre contrôle.  
  
3.  Cliquez sur le nœud Interface de votre contrôle (le deuxième nœud du nœud Bibliothèque) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **ajouter** puis cliquez sur **ajouter une propriété**.  
  
     L’Assistant Ajout de propriété s’ouvre.  
  
5.  Dans le **nom de la propriété** , cliquez sur **police**.  
  
6.  Cliquez sur **Terminer**.  
  
 L’Assistant Ajout de propriété ajoute la ligne suivante à la table de dispatch du contrôle, située dans le fichier d’implémentation :  
  
 [!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]  
  
 En outre, l’Assistant Ajout de propriété ajoute la ligne suivante au contrôle. Fichier IDL :  
  
 [!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]  
  
 La propriété stock Caption est un exemple d’une propriété de texte qui peut être tracée en utilisant les informations de propriété de police stocks. Ajout de la propriété stock Caption au contrôle utilise des étapes similaires à celles utilisées pour la propriété stock Font.  
  
#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Pour ajouter la propriété stock Caption à l’aide de l’Assistant Ajout de propriété  
  
1.  Chargez votre projet de contrôle.  
  
2.  Dans l’Affichage de classes, développez le nœud Bibliothèque de votre contrôle.  
  
3.  Cliquez sur le nœud Interface de votre contrôle (le deuxième nœud du nœud Bibliothèque) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **ajouter** puis cliquez sur **ajouter une propriété**.  
  
     L’Assistant Ajout de propriété s’ouvre.  
  
5.  Dans le **nom de la propriété** , cliquez sur **légende**.  
  
6.  Cliquez sur **Terminer**.  
  
 L’Assistant Ajout de propriété ajoute la ligne suivante à la table de dispatch du contrôle, située dans le fichier d’implémentation :  
  
 [!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]  
  
##  <a name="_core_modifying_the_ondraw_function"></a> Modification de la fonction OnDraw  
 L’implémentation par défaut de `OnDraw` utilise la police système Windows pour tout le texte affiché dans le contrôle. Cela signifie que vous devez modifier le `OnDraw` code en sélectionnant l’objet de police dans le contexte de périphérique. Pour ce faire, appelez [COleControl::SelectStockFont](../mfc/reference/colecontrol-class.md#selectstockfont) et transmettre le contexte de périphérique du contrôle, comme indiqué dans l’exemple suivant :  
  
 [!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]  
  
 Après le `OnDraw` fonction a été modifiée pour utiliser l’objet de police, de n’importe quel texte dans le contrôle s’affiche avec les caractéristiques de la propriété du contrôle stock Font.  
  
##  <a name="_core_using_custom_font_properties_in_your_control"></a> À l’aide des propriétés de la police personnalisée dans votre contrôle  
 En plus de la propriété stock Font, le contrôle ActiveX peut avoir des propriétés personnalisées de la police. Pour ajouter une propriété de police personnalisée, vous devez :  
  
-   Utilisez l’Assistant Ajout de propriété pour implémenter la propriété de police personnalisée.  
  
-   [Traitement des notifications de police](#_core_processing_font_notifications).  
  
-   [Implémentation d’une nouvelle interface de notification de police](#_core_implementing_a_new_font_notification_interface).  
  
###  <a name="_core_implementing_a_custom_font_property"></a> Implémentation d’une propriété de police personnalisée  
 Pour implémenter une propriété de police personnalisée, vous utilisez l’Assistant Ajout de propriété pour ajouter la propriété et puis apporter des modifications au code. Les sections suivantes décrivent comment ajouter personnalisé `HeadingFont` propriété à l’exemple de contrôle.  
  
##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>Pour ajouter la propriété de police personnalisée à l’aide de l’Assistant Ajout de propriété  
  
1.  Chargez votre projet de contrôle.  
  
2.  Dans l’Affichage de classes, développez le nœud Bibliothèque de votre contrôle.  
  
3.  Cliquez sur le nœud Interface de votre contrôle (le deuxième nœud du nœud Bibliothèque) pour ouvrir le menu contextuel.  
  
4.  Dans le menu contextuel, cliquez sur **ajouter** puis cliquez sur **ajouter une propriété**.  
  
     L’Assistant Ajout de propriété s’ouvre.  
  
5.  Dans le **nom de la propriété** , tapez un nom pour la propriété. Pour cet exemple, utilisez **HeadingFont**.  
  
6.  Pour **Type d’implémentation**, cliquez sur **Méthodes Get/Set**.  
  
7.  Dans le **Type de propriété** boîte, sélectionnez **IDispatch\***  pour le type de propriété.  
  
8.  Cliquez sur **Terminer**.  
  
 L’Assistant Ajout de propriété crée le code pour ajouter le `HeadingFont` propriété personnalisée à la `CSampleCtrl` classe et l’exemple. Fichier IDL. Étant donné que `HeadingFont` est un type de propriété Get/Set, l’Assistant Ajout de propriété modifie le `CSampleCtrl` table de dispatch de la classe pour inclure un `DISP_PROPERTY_EX_ID` [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex) entrée de macro :  
  
 [!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]  
  
 Le `DISP_PROPERTY_EX` macro associe le `HeadingFont` avec son nom de la propriété `CSampleCtrl` classe méthodes Get et Set, `GetHeadingFont` et `SetHeadingFont`. Le type de la valeur de propriété est également spécifié ; Dans ce cas, **VT_FONT**.  
  
 L’Assistant Ajout de propriété ajoute également une déclaration dans le fichier d’en-tête (. H) pour le `GetHeadingFont` et `SetHeadingFont` des fonctions et ajoute les modèles de fonction dans le fichier d’implémentation (. CPP) :  
  
 [!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]  
  
 Enfin, l’Assistant Ajout de propriété modifie le contrôle. Fichier IDL en ajoutant une entrée pour le `HeadingFont` propriété :  
  
 [!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]  
  
### <a name="modifications-to-the-control-code"></a>Modifications apportées au Code de contrôle  
 Maintenant que vous avez ajouté le `HeadingFont` propriété au contrôle, vous devez apporter des modifications pour les fichiers d’en-tête et d’implémentation contrôle pour prendre en charge la nouvelle propriété.  
  
 Dans le fichier d’en-tête (. (H), ajoutez la déclaration suivante d’une variable membre protégé :  
  
 [!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]  
  
 Dans le fichier d’implémentation (. (CPP), procédez comme suit :  
  
-   Initialiser `m_fontHeading` dans le constructeur du contrôle.  
  
     [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]  
  
-   Déclarez un statique **FONTDESC** structure contenant les attributs par défaut de la police.  
  
     [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]  
  
-   Dans le contrôle `DoPropExchange` membre fonctionne, ajoutez un appel à la `PX_Font` (fonction). Cela fournit l’initialisation et la persistance de votre propriété de police personnalisée.  
  
     [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]  
  
-   Terminez d’implémenter le contrôle `GetHeadingFont` fonction membre.  
  
     [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]  
  
-   Terminez d’implémenter le contrôle `SetHeadingFont` fonction membre.  
  
     [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]  
  
-   Modifier le contrôle `OnDraw` fonction membre pour définir une variable pour contenir la police sélectionnée précédemment.  
  
     [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]  
  
-   Modifier le contrôle `OnDraw` fonction membre pour sélectionner la police personnalisée dans le contexte de périphérique en ajoutant la ligne suivante partout où la police doit être utilisé.  
  
     [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]  
  
-   Modifier le contrôle `OnDraw` fonction membre pour sélectionner la police précédente dans le contexte de périphérique en ajoutant la ligne suivante une fois que la police a été utilisée.  
  
     [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]  
  
 Une fois que la propriété de police personnalisée a été implémentée, la page de propriétés de police standard doit être implémentée, en permettant aux utilisateurs de contrôle modifier la police du contrôle actuel. Pour ajouter l’ID de page de propriétés de la page de propriétés de police standard, insérez la ligne suivante après la `BEGIN_PROPPAGEIDS` macro :  
  
 [!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]  
  
 Vous devez également incrémenter d’une unité le paramètre count de votre macro `BEGIN_PROPPAGEIDS` . La ligne suivante le montre :  
  
 [!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]  
  
 Après ont apporté ces modifications, régénérez l’ensemble du projet pour incorporer les fonctionnalités supplémentaires.  
  
###  <a name="_core_processing_font_notifications"></a> Traitement des Notifications de police  
 Dans la plupart des cas, le contrôle doit savoir quand les caractéristiques de l’objet de police ont été modifiées. Chaque objet de police est capable de fournir des notifications quand il change en appelant une fonction membre de la **IFontNotification** interface implémentée par `COleControl`.  
  
 Si le contrôle utilise la propriété stock Font, ses notifications sont gérées par le `OnFontChanged` fonction membre de `COleControl`. Lorsque vous ajoutez des propriétés de police personnalisée, vous pouvez les installer à utiliser la même implémentation. Dans l’exemple de la section précédente, cela a été accompli en passant &**m_xFontNotification** lors de l’initialisation du **m_fontHeading** variable membre.  
  
 ![Implémentation de plusieurs interfaces d’objet police](../mfc/media/vc373q1.gif "vc373q1")  
Implémentation de plusieurs Interfaces d’objet Font  
  
 Les lignes pleines dans la figure ci-dessus montrent que les deux objets police utilisent la même implémentation de **IFontNotification**. Cela peut provoquer des problèmes si vous voulez déterminer quelle police modifiée.  
  
 La première consiste à faire la distinction entre les notifications d’objet police du contrôle pour créer une implémentation distincte de la **IFontNotification** interface pour chaque objet de police dans le contrôle. Cette technique vous permet d’optimiser le code de dessin en mettant à jour uniquement la chaîne, ou des chaînes, qui utilisent la police récemment modifiée. Les sections suivantes présentent les étapes nécessaires pour implémenter des interfaces de notification séparées pour une deuxième propriété de police. La deuxième propriété de police est censée pour être le `HeadingFont` propriété qui a été ajoutée dans la section précédente.  
  
###  <a name="_core_implementing_a_new_font_notification_interface"></a> Implémentation d’une nouvelle Interface de Notification de police  
 Pour faire la distinction entre les notifications de deux ou plusieurs polices, une nouvelle interface de notification doit être implémentée pour chaque police utilisée dans le contrôle. Les sections suivantes décrivent comment implémenter une nouvelle interface de notification de police en modifiant les fichiers d’en-tête et d’implémentation de contrôle.  
  
### <a name="additions-to-the-header-file"></a>Ajouts au fichier d’en-tête  
 Dans le fichier d’en-tête (. (H), ajoutez les lignes suivantes à la déclaration de classe :  
  
 [!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]  
  
 Cette opération crée une implémentation de la `IPropertyNotifySink` interface appelée `HeadingFontNotify`. Cette nouvelle interface contient une méthode appelée `OnChanged`.  
  
### <a name="additions-to-the-implementation-file"></a>Ajouts au fichier d’implémentation  
 Dans le code qui initialise la police de titre (dans le constructeur du contrôle), modifiez `&m_xFontNotification` à `&m_xHeadingFontNotify`. Ensuite, ajoutez le code suivant :  
  
 [!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]  
  
 Le `AddRef` et `Release` méthodes dans le `IPropertyNotifySink` interface effectuer le suivi de nombre de références de l’objet de contrôle ActiveX. Lorsque le contrôle obtient l’accès au pointeur d’interface, le contrôle appelle `AddRef` pour incrémenter le décompte de références. Lorsque le contrôle a terminé avec le pointeur, il appelle `Release`, de la même façon que **GlobalFree** peut être appelée pour libérer un bloc de mémoire globale. Lorsque le décompte de références pour cette interface atteint zéro, l’implémentation d’interface peut être libérée. Dans cet exemple, le `QueryInterface` fonction retourne un pointeur vers un `IPropertyNotifySink` interface sur un objet particulier. Cette fonction permet un contrôle ActiveX d’interroger un objet afin de déterminer les interfaces qu’il prend en charge.  
  
 Une fois ces modifications ont été apportées à votre projet, régénérez le projet et utilisez le conteneur de Test pour tester l’interface. Pour plus d’informations sur la façon d’accéder au conteneur de test, consultez la page [Test des propriétés et des événements avec le conteneur de test](../mfc/testing-properties-and-events-with-test-container.md) .  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : Utilisation d’images dans un contrôle ActiveX](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)   
 [Contrôles ActiveX MFC : utilisation des pages de propriétés stock](../mfc/mfc-activex-controls-using-stock-property-pages.md)

