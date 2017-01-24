---
title: "Contr&#244;les ActiveX sur Internet | Microsoft Docs"
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
  - "contrôles ActiveX (C++), créer"
  - "contrôles ActiveX (C++), Internet"
  - "télécharger des données avec des contrôles ActiveX"
  - "applications Internet (C++), contrôles ActiveX"
  - "réseaux (C++), télécharger avec des contrôles ActiveX"
  - "contrôles OLE (C++), mettre à niveau vers ActiveX"
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX sur Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles ActiveX sont la version mise à jour de la spécification de contrôle OLE.  Les contrôles sont une architecture primaire pour le développement de composants logiciels programmables qui peuvent être utilisés dans plusieurs conteneurs, y compris les navigateurs Web COM\-compatibles sur Internet.  Un contrôle ActiveX peut être un contrôle Internet et peut ajouter ses fonctionnalités dans un document actif ou faire partie d'une page Web.  Les contrôles sur une page Web peuvent communiquer entre eux à l'aide de scripts.  
  
 Les contrôles ActiveX ne sont pas limités à Internet.  Un contrôle ActiveX peut également être utilisé dans n'importe quel conteneur, tant que le contrôle prend en charge les interfaces requises par ce conteneur.  
  
 **Les contrôles ActiveX ont plusieurs avantages, notamment :**  
  
-   Moins d'interfaces requises que les contrôles OLE précédents.  
  
-   La possibilité d'être sans fenêtre et toujours actif sur place.  
  
 **Pour être un contrôle ActiveX, un contrôle doit :**  
  
-   Prend en charge l'interface **IUnknown**.  
  
-   Etre un Objet COM  
  
-   Exporter **DLLRegisterServer** et **DLLUnRegisterServer**.  
  
-   Supporter des interfaces additionnelles, comme requis par la fonctionnalité.  
  
## Rendre vos contrôles existants adaptés à Internet  
 Concevoir un contrôle qui fonctionne bien dans un environnement Internet nécessite de faire attention aux débits de transmission relativement faibles sur Internet.  Vous pouvez utiliser les contrôles existants ; toutefois, il existe des étapes que vous devez effectuer pour rendre le nombre d'instructions plus petit et pour effectuer vos téléchargements de propriétés du contrôle de manière asynchrone.  
  
 Pour améliorer les performances des contrôles, suivez ces conseils sur les considérations relatives à l'efficacité :  
  
-   Implémentez les techniques décrites dans l'article [Contrôles ActiveX : Optimisation](../mfc/mfc-activex-controls-optimization.md).  
  
-   Déterminez comment un contrôle est instancié.  
  
-   Soyez asynchrone ; ne retardez pas d'autres programmes.  
  
-   Téléchargez les données par petits blocs.  
  
     En téléchargeant des flux de données tels que des fichiers bitmap ou des données vidéo, accédez aux données d'un contrôle en coopération avec le conteneur.  Récupérez des données de façon incrémentielle ou progressive, en travaillant en coopération avec d'autres contrôles qui peuvent aussi réupérer des données.  Ce code peut également télécharger de manière asynchrone.  
  
-   Téléchargez le code et les propriétés en arrière\-plan.  
  
-   Soyez aussi actif que possible au niveau de l'interface utilisateur.  
  
-   Considérez la manière dont les données permanentes sont enregistrées, à la fois pour les propriétés et les grosses données BLOB \(par exemple une image bitmap ou des données vidéo\).  
  
     Les contrôles avec des quantités importantes de données permanentes, telles que des fichiers bitmap ou AVI, requièrent une attention particulière à la méthode de téléchargement.  Un document ou une page peut être visible dès que possible, et permet à l'utilisateur d'interagir avec la page lorsque les contrôles extraient des données en arrière\-plan.  
  
-   Entrez les routines efficaces pour réduire le nombre et l'exécution d'instructions.  
  
     Les contrôles d'étiquette et de petits boutons, avec seulement quelques octets de données persistantes, conviennent pour une utilisation dans l'environnement Internet et fonctionnent correctement à l'intérieur des navigateurs.  
  
-   Considérez que la progression est communiquée au conteneur.  
  
     Informez le conteneur de la progression du téléchargement asynchrone, notamment lorsque l'utilisateur peut commencer à interagir avec une page, et si le téléchargement terminé.  Le conteneur peut afficher la progression \(tels que les pourcentages complétés\) à l'utilisateur.  
  
-   Déterminez comment les contrôles sont stockés sur l'ordinateur client.  
  
## Création d'un nouveau contrôle ActiveX  
 Lors de la création d'un contrôle avec l'Assistant d'Application, vous pouvez choisir d'activer la prise en charge des monikers asynchrones ainsi que des optimisations supplémentaires.  Pour ajouter la prise en charge des propriétés de téléchargement asynchrone, procédez comme suit :  
  
#### Pour créer votre projet à l'aide de l'Assistant de Contrôle ActiveX MFC  
  
1.  Cliquez sur `New` dans le menu **Fichier**.  
  
2.  Sélectionnez **Assistant Contrôle ActiveX MFC** dans les projets Visual C\+\+ et nommez votre projet.  
  
3.  Dans la page **Paramètres du contrôle**, sélectionnez **Charge les propriétés de façon asynchrone**.  Cette option configure la propriété d'état prêt et l'événement de modification d'état prêt pour vous.  
  
     Vous pouvez également sélectionner des optimisations supplémentaires, telles que **Activation sans fenêtre**, décrit dans [Contrôles ActiveX : Optimisation](../mfc/mfc-activex-controls-optimization.md).  
  
4.  Cliquez sur **Terminer** pour créer le projet.  
  
#### Pour créer une classe dérivée de CDataPathProperty  
  
1.  Créez une classe dérivée de `CDataPathProperty`.  
  
2.  Dans chacun de vos fichiers sources qui contiennent le fichier d'en\-tête pour le contrôle, ajoutez le fichier d'en\-tête pour cette classe avant celui\-ci.  
  
3.  Dans cette classe, remplacez `OnDataAvailable`.  Cette fonction est appelée lorsque les données sont disponibles pour l'affichage.  Lorsque des données deviennent disponibles, vous pouvez les gérer avec la méthode de votre choix, par exemple avec un affichage progressif.  
  
     L'extrait de code ci\-dessous est un exemple simple d'affichage progressif des données dans un contrôle d'édition.  Notez l'utilisation de l'indicateur **BSCF\_FIRSTDATANOTIFICATION** pour désactiver le contrôle d'édition.  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/CPP/activex-controls-on-the-internet_1.cpp)]  
  
     Notez que vous devez inclure AFXCMN.H pour utiliser la classe `CListCtrl`.  
  
4.  Lorsque votre contrôle change d'état général \(par exemple, de "en chargement" à "initialisé" ou "en intéraction utilisateur"\), appelez `COleControl::InternalSetReadyState`.  Si le contrôle a une seule propriété de chemin d'accès aux données, vous pouvez ajouter du code dans **BSCF\_LASTDATANOTIFICATION** pour notifier le conteneur que le téléchargement est terminé.  Par exemple :  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/CPP/activex-controls-on-the-internet_2.cpp)]  
  
5.  Override `OnProgress`.  Dans `OnProgress`, il vous est renvoyé un nombre qui indique la plage maximale et un nombre indiquant l'avancement du téléchargement actuel.  Vous pouvez utiliser ces nombres pour afficher l'état, comme le pourcentage de complétion.  
  
 La procédure suivante ajoute une propriété au contrôle pour utiliser uniquement la classe qui vient d'être dérivée.  
  
#### Pour ajouter une propriété  
  
1.  Dans **Affichage de classes**, cliquez avec le bouton droit sur l'interface sous le nœud de bibliothèque et sélectionnez **Ajouter**, puis **Ajouter une propriété**.  Cela démarre **Assistant Ajout de propriété**.  
  
2.  Dans **Assistant Ajout de propriété**, sélectionnez la case d'option de **Set\/Get Methods**, tapez **Nom de propriété**, par exemple, EditControlText, puis sélectionnez BSTR comme **Type de propriété**.  
  
3.  Cliquez sur **Terminer**.  
  
4.  Déclarez une variable membre de votre classe dérivée de `CDataPathProperty` à votre classe de contrôles ActiveX.  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/CPP/activex-controls-on-the-internet_3.h)]  
  
5.  Implémentez les méthodes **Get\/Set**.  Pour **Get**, renvoyez la chaîne.  Pour `Set`, chargez la propriété et appelez `SetModifiedFlag`.  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/CPP/activex-controls-on-the-internet_4.cpp)]  
  
6.  Dans [DoPropExchange](../Topic/COleControl::DoPropExchange.md), ajoutez la ligne suivante :  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/CPP/activex-controls-on-the-internet_5.cpp)]  
  
7.  Substituez [ResetData](../Topic/CDataPathProperty::ResetData.md) pour notifier la propriété de réinitialiser son contrôle en ajoutant cette ligne :  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/CPP/activex-controls-on-the-internet_6.cpp)]  
  
## Choisir partir de CDataPathProperty ou de CCachedDataPathProperty  
 L'exemple précédent décrit les étapes pour dériver la propriété de votre contrôle de `CDataPathProperty`.  Il s'agit d'un bon choix si vous téléchargez des données en temps réel qui changent fréquemment, et pour lesquelles vous n'avez pas besoin de conserver toutes les données, mais uniquement la valeur actuelle.  Un exemple est un contrôle ticker standard.  
  
 Vous pouvez également dériver `CCachedDataPathProperty`.  Dans ce cas, les données téléchargées sont mises en cache dans un fichier de stockage.  Il s'agit d'un bon choix si vous devez conserver toutes les données téléchargées \(par exemple, un contrôle qui affiche progressivement une bitmap\).  Dans ce cas, la classe possède une variable membre contenant les données :  
  
 `CMemFile m_Cache;`  
  
 Dans la classe de contrôle ActiveX, vous pouvez utiliser ce fichier mappé en mémoire dans `OnDraw` pour afficher les données.  Dans votre classe contrôle ActiveX dérivée `CCachedDataPathProperty`, substituez la fonction membre `OnDataAvailable` et infirmez le contrôle, après avoir appelé l'implémentation de la classe de base.  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/CPP/activex-controls-on-the-internet_7.cpp)]  
  
## Téléharger des donner en mode asynchrone à l'aide de les contrôles ActiveX  
 Les données de téléchargement sur un réseau doivent être effectuées de manière asynchrone.  L'avantage de cette opération est que si un grand nombre de données sont transférées ou si la connexion est lente, l'opération de téléchargement ne bloque pas d'autres processus exécutés sur le client.  
  
 Des monikers asynchrones permettent de télécharger les données asynchrone sur un réseau.  Une opération de lecture dans un moniker asynchrone retourne immédiatement le résultat, même si l'opération n'a pas été effectuée.  
  
 Par exemple, si seuls 10 octets sont disponibles et la lecture est appelée de manière asynchrone dans un fichier 1K, la lecture ne bloque pas, mais retourne les 10 octets disponibles.  
  
 Vous implémentez [monikers asynchrones](../mfc/asynchronous-monikers-on-the-internet.md) en utilisant la classe `CAsyncMonikerFile`.  Toutefois, les contrôles ActiveX peuvent utiliser la classe `CDataPathProperty`, dérivée de `CAsyncMonikerFile`, pour implémenter des propriétés du contrôle asynchrones.  
  
 L'exemple de ASYNDOWN montre comment configurer une boucle asynchrone en utilisant des timers pour lire les données.  ASYNDOWN est décrit en détail dans l'article de la Base de connaissances « HOWTO : AsyncDown illustre le téléchargement asynchrone de données » \(Q177244\) et peut être téléchargé à partir du Centre de téléchargement Microsoft. \(Pour plus d'informations sur le téléchargement classe à partir de le Centre de téléchargement Microsoft, consultez l'article « comment obtenir des fichiers de support technique Microsoft depuis les services en ligne » \(Q119591\) dans la Base de connaissances Microsoft.\) Vous trouverez les articles de Base de connaissances sur le CD\-ROM de la bibliothèque MSDN ou à l'adresse [http:\/\/support.microsoft.com\/support](http://support.microsoft.com/support).  
  
 La technique de base utilisée dans ASYNDOWN consiste à définir une horloge dans **CDataPathProperty::OnDataAvailable** pour montrer quand les données sont disponibles.  Si le message du minuteur est accepté, elle lit dans des blocs de 128 octets de données et remplit un contrôle d'édition.  Si les données ne sont pas disponibles lorsque le message du minuteur est traité, le minuteur est désactivé.  `OnDataAvailable` démarre l'horloge si plus de données arrivent ultérieurement.  
  
## Afficher un contrôle dans une page Web  
 Voici un exemple de tag et d'attributs d'objet pour insérer un contrôle dans une page Web.  
  
 `<OBJECT`  
  
 `CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"`  
  
 `CODEBASE="/ie/download/activex/iechart.ocx"`  
  
 `ID=chart1`  
  
 `WIDTH=400`  
  
 `HEIGHT=200`  
  
 `ALIGN=center`  
  
 `HSPACE=0`  
  
 `VSPACE=0`  
  
 `>`  
  
 `<PARAM NAME="BackColor" value="#ffffff">`  
  
 `<PARAM NAME="ForeColor" value="#0000ff">`  
  
 `<PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt">`  
  
 `</OBJECT>`  
  
## Mettre à jour un contrôle OLE existant pour utiliser les nouvelles fonctionnalités du contrôle ActiveX  
 Si votre contrôle utilisateur a été créé avec une version de Visual C\+\+ antérieure à 4.2, il existe des étapes que vous pouvez suivre pour améliorer ses performances et ses fonctionnalités.  Pour une présentation détaillée de ces modifications, consultez [Contrôles ActiveX : Optimisation](../mfc/mfc-activex-controls-optimization.md).  
  
 Si vous ajoutez la prise en charge des propriétés asynchrones à un contrôle existant, vous devez ajouter la propriété d'état prêt et l'événement de `ReadyStateChange` vous\-même.  Dans le constructeur de votre contrôle, ajoutez :  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/CPP/activex-controls-on-the-internet_8.cpp)]  
  
 Vous allez mettre à jour l'état prêt tandis que votre code est téléchargé en appelant [COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md).  Un emplacement que vous pouvez appeler `InternalSetReadyState` est de la substitution de `OnProgress` de classe dérivée de `CDataPathProperty`.  
  
 Ensuite, suivez les étapes dans [Création d'un contrôle ActiveX](#_core_how_do_i_create_a_new_activex_control.3f).  
  
## Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)