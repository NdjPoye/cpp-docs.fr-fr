---
title: "Example: Implementing a Property Page | Microsoft Docs"
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
  - "pages de propriétés, implémenter"
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Example: Implementing a Property Page
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment générer une page de propriétés qui affiche \(et vous permet à la modification\) des propriétés de l'interface de [Classes de documents](../mfc/document-classes.md) .  Cette interface est exposée par des documents dans [Exemples du modèle objet d'environnement commun](../Topic/Common%20Environment%20Object%20Model%20Examples.md) de Visual Studio \(bien que la page de propriétés que vous créerez ne s'inquiétera pas d'où les objets qui manipule venu tant que ils prennent en charge l'interface appropriée\).  
  
 L'exemple est basé sur [Exemple ATLPages](../top/visual-cpp-samples.md).  
  
 Pour exécuter cet exemple, vous voulez bien :  
  
-   [Ajoutez la classe de page de propriétés ATL](#vcconusing_the_atl_object_wizard) à l'aide de la boîte de dialogue de classe d'ajout et de l'Assistant Page de propriétés ATL.  
  
-   [Modifiez la ressource de boîte de dialogue](#vcconediting_the_dialog_resource) en ajoutant de nouveaux contrôles pour les propriétés intéressantes de l'interface de **Document** .  
  
-   [ajoutez les gestionnaires de messages](#vcconadding_message_handlers) pour contenir le site de page de propriétés informés des modifications effectuées par l'utilisateur.  
  
-   Ajoutez des instructions d' `#import` et un typedef dans la section de [gestion interne](#vcconhousekeeping) .  
  
-   [substituez IPropertyPageImpl::SetObjects](#vcconoverriding_ipropertypageimpl_setobjects) pour valider des objets passés à la page de propriétés.  
  
-   [substitution IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate) pour initialiser l'interface de la page de propriétés.  
  
-   [substitution IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply) pour mettre à jour l'objet avec les dernières valeurs de propriété.  
  
-   [affichez la page de propriétés](#vccontesting_the_property_page) en créant un objet d'assistance simple.  
  
-   [Créez une macro](#vcconcreating_a_macro) qui tester la page de propriétés.  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> Ajouter la classe de page de propriétés ATL  
 D'abord, créez un projet ATL pour un serveur de DLL appelée `ATLPages7`.  Utilisez maintenant [Assistant Page de propriétés ATL](../atl/reference/atl-property-page-wizard.md) pour générer une page de propriétés.  Donnez à la page de propriétés **Nom court** de **DocProperties** puis de basculez vers la page de **Chaînes** aux éléments de propriété\-page\- spécifique de définir comme indiqué dans le tableau ci\-dessous.  
  
|Élément|Valeur|  
|-------------|------------|  
|Titre|TextDocument|  
|Chaîne de documents|Propriétés de VCUE TextDocument|  
|Helpfile|*\<blank\>*|  
  
 Les valeurs que vous définissez dans cette page de l'assistant sont retournées au conteneur de page de propriétés lorsqu'il appelle **IPropertyPage::GetPageInfo**.  Ce qui arrive aux chaînes ensuite qui dépend du conteneur, mais généralement ils sont utilisés pour identifier votre page à l'utilisateur.  Le titre s'affiche généralement dans un onglet au\-dessus de votre page et la chaîne de document peut être affichée dans une barre d'état ou une info\-bulle \(bien que le frame de propriété standard n'utilise pas cette chaîne du tout\).  
  
> [!NOTE]
>  Les chaînes que vous définissez ici sont stockées comme des ressources de type chaîne dans votre projet par l'assistant.  Vous pouvez facilement modifier ces chaînes à l'aide de l'éditeur de ressources si vous devez modifier ces informations après le code de votre page a été généré.  
  
 Cliquez sur **OK** pour effectuer la génération à l'assistant votre page de propriétés.  
  
##  <a name="vcconediting_the_dialog_resource"></a> Modifier la ressource de boîte de dialogue  
 Maintenant que votre page de propriétés a été générée, vous devrez ajouter des contrôles à la ressource de boîte de dialogue qui représente votre page.  Ajoutez une zone d'édition, un contrôle de texte statique, et une case à cocher et définissez leurs ID comme indiqué ci\-dessous :  
  
 ![Modification d'une ressource de boîte de dialogue](../atl/media/ppgresourcelabeled.png "PPGResourceLabeled")  
  
 Ces contrôles sont utilisés pour afficher le nom de fichier du document et de son état en lecture seule.  
  
> [!NOTE]
>  La ressource de boîte de dialogue n'inclut pas de frame ou des boutons de commande, ni elle a l'apparence à onglets que vous pouvez s'être attendu.  Ces fonctionnalités sont fournies par un frame de page de propriétés telles que celui créé en appelant [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437).  
  
##  <a name="vcconadding_message_handlers"></a> Ajouter des gestionnaires de messages  
 Avec les contrôles en place, vous pouvez ajouter des gestionnaires de messages pour mettre à jour l'état modifié de la page lorsque la valeur de l'un ou l'autre des instructions break de contrôles :  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/CPP/example-implementing-a-property-page_1.h)]  
  
 Ce code répond aux modifications apportées au contrôle d'édition ou la case à cocher en appelant [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md), qui signale au site de page que la page a changé.  En général le site de page répondra en activant ou désactivant un bouton de **Appliquer** sur le frame de page de propriétés.  
  
> [!NOTE]
>  Dans vos propres pages de propriétés, vous devrez peut\-être effectuer précisément que les propriétés ont été modifié par l'utilisateur afin que vous puissiez éviter de mettre à jour les propriétés qui n'ont pas été modifiées.  Outils de cet exemple que le code en maintenant les valeurs de propriété d'origine et en les comparant avec les valeurs actuelles de l'interface utilisateur lorsqu'il est temps d'appliquer les modifications.  
  
##  <a name="vcconhousekeeping"></a> Gestion interne  
 Ajoutez maintenant des instructions d' `#import` à DocProperties.h afin que le compilateur sache l'interface de **Document** :  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/CPP/example-implementing-a-property-page_2.h)]  
  
 Vous devez également faire référence à la classe de base d' `IPropertyPageImpl` ; ajoutez `typedef` suivant à la classe de **CDocProperties** :  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/CPP/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> Substituer IPropertyPageImpl::SetObjects  
 La première méthode d' `IPropertyPageImpl` que vous devez substituer est [SetObjects](../Topic/IPropertyPageImpl::SetObjects.md).  Voici que vous ajouterez du code pour vérifier qu'un objet unique a été passé et qu'il prend en charge l'interface de **Document** que vous attendez :  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/CPP/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  Il est logique de prendre en charge un objet unique pour cette page car vous permettrez à l'utilisateur de définir le nom de fichier de l'objet — un seul fichier peut exister à tout un emplacement.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> Substituer IPropertyPageImpl::Activate  
 L'étape suivante consiste à initialiser la page de propriétés avec les valeurs de propriété de l'objet sous\-jacent lorsque la page est d'abord créée.  
  
 Dans ce cas vous devez ajouter les membres suivants à la classe comme vous utiliserez également les valeurs de propriété initiales pour la comparaison lorsque les utilisateurs de la page appliquent leurs modifications :  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/CPP/example-implementing-a-property-page_5.h)]  
  
 L'implémentation de la classe de base de la méthode d' [Exécutez](../Topic/IPropertyPageImpl::Activate.md) est chargé de créer la boîte de dialogue et ses contrôles, vous pouvez substituer cette méthode et ajoutez votre propre initialisation après avoir appelé la classe de base :  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/CPP/example-implementing-a-property-page_6.h)]  
  
 Ce code utilise les méthodes COM d'interface de **Document** pour obtenir des propriétés qui vous intéresse.  Il utilise ensuite les wrappers de l'API Win32 fournis par [CDialogImpl](../atl/reference/cdialogimpl-class.md) et ses classes de base pour afficher les valeurs de propriété à l'utilisateur.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> Substituer IPropertyPageImpl::Apply  
 Lorsque les utilisateurs souhaitent appliquer leurs modifications apportées aux objets, le site de page de propriétés appelle la méthode d' [appliquez](../Topic/IPropertyPageImpl::Apply.md) .  Il s'agit de l'emplacement pour effectuer l'inverse du code dans **Activate** — alors qu' **Activate** a pris des valeurs de l'objet et les a envoyées dans les contrôles de la page de propriétés, **Appliquer** prend les valeurs des contrôles de la page de propriétés et les pousse dans l'objet.  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/CPP/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  Le contrôle sur [m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md) au début de cette implémentation est un premier contrôle pour éviter les mises à jour inutiles les objets si **Appliquer** est appelé plusieurs fois.  Il existe également des contrôles sur chacune des valeurs de propriété de vérifier que les modifications entraînent un appel de méthode à **Document**.  
  
> [!NOTE]
>  Expose **NomComplet** de**Document** en tant que propriété en lecture seule.  Pour mettre à jour le nom de fichier du document en fonction de les modifications apportées à la page de propriétés, vous devez utiliser la méthode **Enregistrer** pour enregistrer le fichier sous un nom différent.  Ainsi, le code d'une page de propriétés ne doit pas se limiter à obtenir ou de définir des propriétés.  
  
##  <a name="vccontesting_the_property_page"></a> Affichage de la page de propriétés  
 Pour afficher cette page, vous devez créer un objet d'assistance simple.  L'objet d'assistance fournit une méthode qui simplifie l'API d' **OleCreatePropertyFrame** pour afficher un connecté d'une page à un objet unique.  Ce programme d'assistance est conçu afin qu'il puisse être utilisé de Visual Basic.  
  
 Utilisez [ajoutez la boîte de dialogue de classe](../ide/add-class-dialog-box.md) et [Assistant Objet simple ATL](../atl/reference/atl-simple-object-wizard.md) pour générer une nouvelle classe et utiliser `Helper` comme son nom court.  Une fois créé, ajoutez une méthode comme indiqué dans le tableau ci\-dessous.  
  
|Élément|Valeur|  
|-------------|------------|  
|Nom de la méthode|`ShowPage`|  
|Paramètres|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 Le paramètre d' `bstrCaption` est la légende à afficher comme titre de la boîte de dialogue.  Le paramètre d' `bstrID` est une chaîne qui représente le CLSID ou un progid de la page de propriétés pour afficher.  Le paramètre d' `pUnk` sera le pointeur d' `IUnknown` de l'objet dont les propriétés sont configurées par la page de propriétés.  
  
 Implémentez la méthode comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/CPP/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> Créer une macro  
 Une fois que vous avez généré le projet, vous pouvez tester la page de propriétés et l'objet d'assistance à l'aide d'une macro simple que vous pouvez créer et exécuter dans l'environnement de développement Visual Studio.  Cette macro crée un objet d'assistance, puis appelle sa méthode de **ShowPage** à l'aide de l'identificateur programmatique de la page de propriétés de **DocProperties** et du pointeur d' **IUnknown** du document active dans l'éditeur Visual Studio.  Le code que vous avez besoin pour cette macro est indiqué ci\-dessous :  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
  
Public Module AtlPages  
  
    Public Sub Test()  
        Dim Helper  
        Helper = CreateObject("ATLPages7.Helper.1")  
  
        On Error Resume Next  
        Helper.ShowPage( _  
            ActiveDocument.Name, _  
            "ATLPages7Lib.DocumentProperties.1", _  
            DTE.ActiveDocument _  
            )  
    End Sub  
  
End Module  
```  
  
 Lorsque vous exécutez cette macro, la page de propriétés s'affiche et le nom de fichier et l'état en lecture seule actuel \- texte du document actif.  L'état de lecture seule du document indique uniquement la possibilité d'écrire au document dans l'environnement de développement ; il n'affecte pas l'attribut de lecture seule du fichier sur le disque.  
  
## Voir aussi  
 [Pages de propriétés](../atl/atl-com-property-pages.md)   
 [Exemple ATLPages](../top/visual-cpp-samples.md)