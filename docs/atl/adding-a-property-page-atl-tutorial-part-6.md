---
title: "Ajout d&#39;une page de propri&#233;t&#233;s (Didacticiel ATL, Partie&#160;6) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: df80d255-e7ea-49d9-b940-3f012e90cf9b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Ajout d&#39;une page de propri&#233;t&#233;s (Didacticiel ATL, Partie&#160;6)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les pages de propriétés sont implémentées en tant qu'objets COM distincts, les permettent à partager si nécessaire.  Dans cette étape, vous allez les tâches suivantes pour ajouter une page de propriétés au contrôle :  
  
-   Création de la ressource en page de propriétés  
  
-   Ajout de code pour créer et gérer la page de propriétés  
  
-   Ajouter la page de propriétés au contrôle  
  
## Création de la ressource en page de propriétés  
 Pour ajouter une page de propriétés à votre contrôle, utilisez ATL ajoute l'assistant de classe.  
  
#### Pour ajouter une page de propriétés  
  
1.  Dans l'explorateur de solutions, polygone de bouton droit.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
3.  Dans la liste de modèles, **Page de propriétés ATL** sélectionnez et de clic **Ajouter**.  
  
4.  Lorsque l'Assistant Page de propriétés ATL apparaît, entrez `PolyProp` comme nom **Court** .  
  
5.  Cliquez sur **Chaînes** pour ouvrir la page **Chaînes** et d'entrer **&Polygon** comme **Titre**.  
  
     **Titre** De la page de propriétés est la chaîne qui s'affiche dans l'onglet pour cette page.  **Chaîne de documents** Est une description qu'un frame de propriété utilise pour mettre dans une ligne d'état ou une info\-bulle.  Notez que le frame de propriété standard en cours n'utilise pas cette chaîne, vous pouvez la laisser avec le contenu par défaut.  Vous ne générerez pas **Fichier d’aide** à l'heure actuelle, vous supprimez l'entrée dans cette zone de texte.  
  
6.  Cliquez sur **Terminé**, et l'objet page de propriétés sera créé.  
  
 Les trois fichiers suivants sont créés :  
  
|Fichier|Description|  
|-------------|-----------------|  
|PolyProp.h|Contient la classe `CPolyProp`C\+\+, qui implémente la page de propriétés.|  
|PolyProp.cpp|Inclut le fichier de PolyProp.h.|  
|PolyProp.rgs|Le script de Registre qui stocke l'objet page de propriétés.|  
  
 Les modifications de code suivantes sont également apportées :  
  
-   La nouvelle page de propriétés est ajoutée au mappage d'entrée d'objet dans Polygon.cpp.  
  
-   La classe d' `PolyProp` est ajoutée au fichier de Polygon.idl.  
  
-   Le nouveau fichier de script PolyProp.rgs de Registre est ajouté à la ressource du projet.  
  
-   Un modèle de boîte de dialogue est ajouté à la ressource du projet pour la page de propriétés.  
  
-   Les chaînes de propriété que vous avez spécifiées sont ajoutées à la table de chaînes de ressource.  
  
 Ajoutez maintenant les champs que vous souhaitez afficher dans la page de propriétés.  
  
#### Pour ajouter des champs à la page de propriétés  
  
1.  Dans l'explorateur de solutions, double\-cliquez sur le fichier de ressources de Polygon.rc.  Cela ouvre l'affichage des ressources.  
  
2.  Dans l'affichage des ressources, développez le nœud de dialogue et double\-cliquez sur IDD\_POLYPROP.  Notez que la boîte de dialogue qui s'affiche est vide à l'exception d'une étiquette qui vous indique insérer les contrôles ici.  
  
3.  Sélectionnez cette étiquette et affectez \-lui la pour lire `côtés :` en modifiant le texte **Légende** dans la fenêtre **Propriétés** .  
  
4.  Redimensionnez la zone d'étiquette afin qu'il ajuste la taille du texte.  
  
5.  Faites glisser un contrôle d'édition de la boîte à outils à droite de l'étiquette.  
  
6.  Enfin, remplacez **ID** du contrôle d'édition par `IDC_SIDES` à l'aide de la fenêtre Propriétés.  
  
 Cela complète le processus de création de la ressource en page de propriétés.  
  
## Ajout de code pour créer et gérer la page de propriétés  
 Maintenant que vous avez créé la ressource en page de propriétés, vous devez écrire le code d'implémentation.  
  
 D'abord, laissez la classe d' `CPolyProp` de définir le nombre de côtés de votre objet lorsque le bouton **Appliquer** est enfoncé.  
  
#### Pour modifier l'application fonctionnent pour définir le nombre de côtés  
  
1.  Remplacez la fonction d' `Apply` dans PolyProp.h par le code suivant :  
  
     [!code-cpp[NVC_ATL_Windowing#58](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_1.h)]  
  
 Une page de propriétés peut avoir plusieurs client lié à celui\-ci à la fois, les boucles de fonction d' `Apply` autour et appelle `put_Sides` sur chaque client avec la valeur extraite de la zone d'édition.  Vous utilisez la classe de [CComQIPtr](../atl/reference/ccomqiptr-class.md) , qui exécute `QueryInterface` sur chaque objet pour obtenir l'interface d' `IPolyCtl` de l'interface d' **IUnknown** \(stockée dans le tableau d' `m_ppUnk` \).  
  
 Le code vérifie ensuite que la définition de la propriété d' `Sides` a fonctionné réellement.  S'il échoue, le code affiche un message affichant des erreurs de l'interface d' **IErrorInfo** .  En général, un conteneur demande un objet l'interface d' **ISupportErrorInfo** et appelle `InterfaceSupportsErrorInfo` d'abord, pour déterminer si l'objet prend en charge des informations sur les erreurs de configuration.  Vous pouvez ignorer cette tâche.  
  
 [CComPtr](../atl/reference/ccomptr-class.md) vous permet en gérant automatiquement le décompte de références, vous n'avez pas besoin d'appeler `Release` sur l'interface.  `CComBSTR` vous aide à `BSTR` traitement, vous ne devez pas effectuer l'appel final d' `SysFreeString` .  Vous utilisez également l'une des classes de conversion de chaînes, vous pouvez convertir `BSTR` si nécessaire \(c'est pourquoi la macro d' `USES_CONVERSION` est au début de la fonction\).  
  
 Vous devez également affecter à l'indicateur modifiée de la page de propriétés pour indiquer que le bouton **Appliquer** doit être activé.  Cela se produit lorsque l'utilisateur modifie la valeur dans la zone d'édition **Côté** .  
  
#### Pour gérer le bouton de l'application  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur CPolyProp et cliquez sur **Propriétés** dans le menu contextuel.  
  
2.  Dans la fenêtre Propriétés, cliquez sur l'icône **Événements** .  
  
3.  Développez la liste de nœud d' `IDC_SIDES` dans l'événement.  
  
4.  `EN_CHANGE`sélectionnez, puis dans la zone déroulante à droite, cliquez sur **\<Add\>  OnEnChangeSides**.  La déclaration de gestionnaire d' `OnEnChangeSides` sera ajoutée à Polyprop.h, et à l'implémentation du gestionnaire à Polyprop.cpp.  
  
 Ensuite, vous modifierez le gestionnaire.  
  
#### Pour modifier la méthode d'OnEnChangeSides  
  
1.  Ajoutez le code suivant dans Polyprop.cpp à la méthode d' `OnEnChangeSides` \(supprimant tout code qui l'assistant mis y\) :  
  
     [!code-cpp[NVC_ATL_Windowing#59](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_2.cpp)]  
  
 `OnEnChangeSides` sera appelé lorsqu'un message d' **WM\_COMMAND** est envoyé à la notification d' **EN\_CHANGE** pour le contrôle d' `IDC_SIDES` .  `OnEnChangeSides` appelle ensuite `SetDirty` et passe `TRUE` pour indiquer la page de propriétés est maintenant modifié et le bouton **Appliquer** doit être activé.  
  
## Ajouter la page de propriétés au contrôle  
 ATL ajoute l'assistant de classe et Assistant Page de propriétés ATL n'ajoutez pas la page de propriétés à votre contrôle automatiquement, parce qu'il peut y avoir plusieurs contrôles dans votre projet.  Vous devez ajouter une entrée au mappage de propriété du contrôle.  
  
#### Pour ajouter la page de propriétés  
  
1.  Ouvrez PolyCtl.h et ajoutez cette ligne au mappage de propriété :  
  
     [!code-cpp[NVC_ATL_Windowing#60](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_3.h)]  
  
 Recherche du mappage de propriété du contrôle à présent se présente comme suit :  
  
 [!code-cpp[NVC_ATL_Windowing#61](../atl/codesnippet/CPP/adding-a-property-page-atl-tutorial-part-6_4.h)]  
  
 Vous pouvez avoir ajouté une macro d' `PROP_PAGE` avec le CLSID de votre page de propriétés, mais si vous utilisez la macro d' `PROP_ENTRY` comme indiqué, la valeur de propriété d' `Sides` est également enregistré lorsque le contrôle est enregistré.  
  
 Les trois paramètres à la macro sont la description de la propriété, le DISPID de la propriété, et le CLSID de la page de propriétés qui possède la propriété sur.  Cela est utile si, par exemple, vous chargez le contrôle dans Visual Basic et définissez le nombre de côtés au moment de le design.  Étant donné que le nombre de côtés est enregistré, lorsque vous rechargez le projet Visual Basic, le nombre de côtés sera restauré.  
  
## Génération et test du contrôle  
 Maintenant générer ce contrôle et insérez\- le dans ActiveX Control Test Container.  Dans l'outil Test Container, dans le menu **Modifier** , cliquez sur **objet de classe de PolyCtl**.  La page de propriétés s'affiche ; cliquez sur **Polygone** tableau.  
  
 Le bouton **Appliquer** est initialement désactivé.  Commencez à taper une valeur dans la zone **Côté** et le bouton **Appliquer** deviendra activé.  Après avoir terminé d'entrer la valeur, cliquez sur le bouton **Appliquer** .  Les modifications affichage, et le bouton **Appliquer** est encore désactivées.  Test écrivant une valeur non valide.  Vous verrez un message contenant la description de l'erreur que vous définissez le de la fonction d' `put_Sides` .  
  
 Ensuite, vous allez votre contrôle sur une page Web.  
  
 [Pour revenir à l'étape 5](../atl/adding-an-event-atl-tutorial-part-5.md) &#124; [Sur à l'étape 7](../atl/putting-the-control-on-a-web-page-atl-tutorial-part-7.md)  
  
## Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)