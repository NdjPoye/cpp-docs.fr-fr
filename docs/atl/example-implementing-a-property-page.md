---
title: Implémentation d’une Page de propriétés (ATL) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 139bdd9076e99139f4da105b4bb2b375689efe15
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="example-implementing-a-property-page"></a>Exemple : Implémentation d’une Page de propriétés
Cet exemple montre comment créer une page de propriétés qui affiche (et permet de modifier) les propriétés de la [Classes de documents](../mfc/document-classes.md) interface.  
  
 L’exemple est basé sur le [exemple ATLPages](../visual-cpp-samples.md).  
  
 Pour exécuter cet exemple, vous allez :  
  
- [Ajouter la classe de page de propriétés ATL](#vcconusing_the_atl_object_wizard) à l’aide de la boîte de dialogue Ajouter une classe et l’Assistant Page de propriétés ATL.  
  
- [Modifier la ressource de boîte de dialogue](#vcconediting_the_dialog_resource) en ajoutant de nouveaux contrôles aux propriétés intéressantes de la **Document** interface.  
  
- [Ajouter des gestionnaires de messages](#vcconadding_message_handlers) pour conserver le site de la page propriété informé des modifications effectuées par l’utilisateur.  
  
-   Ajouter certains `#import` instructions et un typedef dans le [maintenance](#vcconhousekeeping) section.  
  
- [Substituer IPropertyPageImpl::SetObjects](#vcconoverriding_ipropertypageimpl_setobjects) pour valider les objets passés à la page de propriétés.  
  
- [Substituer IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate) pour initialiser l’interface de la page de propriétés.  
  
- [Substituer IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply) pour mettre à jour l’objet avec les dernières valeurs de propriété.  
  
- [Afficher la page de propriétés](#vccontesting_the_property_page) en créant un objet d’assistance simple.  
  
- [Créer une macro](#vcconcreating_a_macro) qui testera la page de propriétés.  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> Ajout de la classe de Page de propriétés ATL  
 Commencez par créer un nouveau projet ATL pour un serveur DLL appelé `ATLPages7`. Utilisez maintenant le [Assistant Page de propriétés ATL](../atl/reference/atl-property-page-wizard.md) pour générer une page de propriétés. Donnez à la page de propriétés un **nom court** de **DocProperties** vous basculez ensuite vers le **chaînes** page pour définir les éléments de la propriété page-spécifiques comme indiqué dans le tableau ci-dessous.  
  
|Élément|Value|  
|----------|-----------|  
|Titre|TextDocument|  
|Chaîne du document|Propriétés VCUE TextDocument|  
|HelpFile|*\<vide >*|  
  
 Les valeurs que vous définissez dans cette page de l’Assistant seront affichera pour le conteneur de page de propriété lorsqu’il appelle **IPropertyPage::GetPageInfo**. Que se passe-t-il pour les chaînes après dépend du conteneur, mais en général, ils seront permet d’identifier votre page à l’utilisateur. Le titre s’affichent généralement dans un onglet au-dessus de votre page et la chaîne Doc peuvent s’afficher dans une barre d’état ou l’info-bulle (bien que le frame de propriété standard n’utilise pas du tout cette chaîne).  
  
> [!NOTE]
>  Les chaînes que vous définissez ici sont stockées en tant que ressources de chaîne dans votre projet par l’Assistant. Vous pouvez facilement modifier ces chaînes à l’aide de l’éditeur de ressources si vous devez modifier ces informations après que le code de votre page a été généré.  
  
 Cliquez sur **OK** pour que l’Assistant génère votre page de propriétés.  
  
##  <a name="vcconediting_the_dialog_resource"></a> Modification de la ressource de boîte de dialogue  
 Maintenant que votre page de propriétés a été généré, vous devez ajouter des contrôles à la ressource de boîte de dialogue représentant votre page. Ajouter une zone d’édition, un contrôle de texte statique et une case à cocher et définissez leurs ID comme indiqué ci-dessous :  
  
 ![Modification d’une ressource de boîte de dialogue](../atl/media/ppgresourcelabeled.gif "ppgresourcelabeled")  
  
 Ces contrôles sont utilisés pour afficher le nom de fichier du document et son état en lecture seule.  
  
> [!NOTE]
>  La ressource de boîte de dialogue n’inclut pas un frame ou commande des boutons, et n’a pas l’apparence à onglets que vous pouvez vous attendre. Ces fonctionnalités sont fournies par un cadre de la page propriété tel que celui créé en appelant [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437).  
  
##  <a name="vcconadding_message_handlers"></a> Ajout de gestionnaires de messages  
 Avec les contrôles en place, vous pouvez ajouter des gestionnaires de messages pour mettre à jour l’état modifié de la page lorsque la valeur de l’un des contrôles change :  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]  
  
 Ce code répond aux modifications apportées au contrôle d’édition ou de la case à cocher en appelant [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty), qui informe le site de la page que la page a changé. En général, la page répond en activant ou désactivant une **appliquer** bouton dans le cadre de la page Propriétés.  
  
> [!NOTE]
>  Dans vos propres pages de propriétés, vous devrez peut-être suivre précisément les propriétés qui ont été modifiées par l’utilisateur afin que vous pouvez éviter la mise à jour des propriétés qui n’ont pas été modifiées. Cet exemple implémente ce code par le suivi de valeurs de propriété d’origine et en les comparant avec les valeurs actuelles de l’interface utilisateur lorsqu’il est temps d’appliquer les modifications.  
  
##  <a name="vcconhousekeeping"></a> Nettoyage  
 Maintenant, ajoutez deux `#import` DocProperties.h des instructions afin que le compilateur connaît le **Document** interface :  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]  
  
 Vous devez également faire référence à la `IPropertyPageImpl` classe de base, ajoutez le code suivant `typedef` à la **CDocProperties** classe :  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> Substitution de IPropertyPageImpl::SetObjects  
 La première `IPropertyPageImpl` méthode que vous devez substituer est [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects). Ici vous allez ajouter du code pour vérifier qu’un seul objet a été passé et qu’il prend en charge la **Document** interface que vous attendez :  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  Il est judicieux pour prendre en charge qu’un seul objet de cette page, car vous ne permettent pas l’utilisateur de définir le nom de fichier de l’objet, un seul fichier peut exister en tout point.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> Substitution de IPropertyPageImpl::Activate  
 L’étape suivante consiste à initialiser la page de propriétés avec les valeurs de propriété de l’objet sous-jacent lors de la création de la page.  
  
 Dans ce cas, vous devez ajouter les membres suivants à la classe, car vous allez également utiliser les valeurs initiales des propriétés pour la comparaison lors de la page appliquer les modifications :  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]  
  
 L’implémentation de classe de base de la [activer](../atl/reference/ipropertypageimpl-class.md#activate) méthode est responsable de la création de la boîte de dialogue et ses contrôles, donc vous pouvez substituer cette méthode et ajouter votre propre initialisation après l’appel de la classe de base :  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]  
  
 Ce code utilise les méthodes COM de le **Document** interface à obtenir les propriétés qui vous intéressent. Il utilise ensuite les wrappers de l’API Win32 fournis par [CDialogImpl](../atl/reference/cdialogimpl-class.md) et ses classes de base pour afficher les valeurs de propriété à l’utilisateur.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> Substitution de IPropertyPageImpl::Apply  
 Lorsque les utilisateurs souhaitent appliquer leurs modifications aux objets, le site de la page propriété appellera la [appliquer](../atl/reference/ipropertypageimpl-class.md#apply) (méthode). C’est là que pour effectuer l’opération inverse du code dans **activer** , tandis que **activer** prend les valeurs de l’objet et les placé dans les contrôles sur la page de propriétés, **appliquer** prend les valeurs des contrôles de la page de propriétés et les transmet à l’objet.  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  La vérification par rapport aux [m_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) au début de cette implémentation est une vérification initiale pour éviter les mises à jour inutiles des objets si **appliquer** est appelée plusieurs fois. Il existe également des vérifications par rapport à chacune des valeurs de propriété pour s’assurer que seules les modifications apportées entraînent dans un appel de méthode à la **Document**.  
  
> [!NOTE]
> **Document** expose **FullName** comme une propriété en lecture seule. Pour mettre à jour le nom de fichier du document en fonction des modifications apportées à la page de propriétés, vous devez utiliser le **enregistrer** méthode pour enregistrer le fichier avec un nom différent. Par conséquent, le code dans une page de propriétés ne doit pas nécessairement se limiter à obtenir ou définir des propriétés.  
  
##  <a name="vccontesting_the_property_page"></a> Affichage de la Page de propriétés  
 Pour afficher cette page, vous devez créer un objet d’assistance simple. L’objet d’assistance fournit une méthode qui simplifie le **OleCreatePropertyFrame** API permettant d’afficher une page unique connecté à un objet unique. Cet objet est conçu afin qu’il peut être utilisé à partir de Visual Basic.  
  
 Utiliser le [boîte de dialogue Ajouter une classe](../ide/add-class-dialog-box.md) et [Assistant objet Simple ATL](../atl/reference/atl-simple-object-wizard.md) pour générer une nouvelle classe et utilisez `Helper` comme nom abrégé. Une fois créé, ajoutez une méthode, comme indiqué dans le tableau ci-dessous.  
  
|Élément|Value|  
|----------|-----------|  
|Nom de la méthode|`ShowPage`|  
|Paramètres|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 Le `bstrCaption` paramètre correspond à la légende à afficher comme titre de la boîte de dialogue. Le `bstrID` paramètre est une chaîne représentant un CLSID ou ProgID de la page de propriétés à afficher. Le `pUnk` paramètre sera le `IUnknown` pointeur de l’objet dont les propriétés sont configurées par la page de propriétés.  
  
 Implémentez la méthode comme indiqué ci-dessous :  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> Création d’une Macro  
 Une fois que vous avez créé le projet, vous pouvez tester la page de propriétés et l’objet d’assistance à l’aide d’une macro simple que vous pouvez créer et exécuter dans l’environnement de développement Visual Studio. Cette macro crée un programme d’assistance de l’objet, puis appelez ses **ShowPage** méthode à l’aide de l’identificateur ProgID de le **DocProperties** page de propriétés et le **IUnknown** pointeur du document actuellement actifs dans l’éditeur Visual Studio. Le code que vous avez besoin pour cette macro est indiqué ci-dessous :  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
 
Public Module AtlPages  
 
    Public Sub Test()  
    Dim Helper  
    Helper = CreateObject("ATLPages7.Helper.1")  
 
    On Error Resume Next  
    Helper.ShowPage(_ 
    ActiveDocument.Name,
    _ 
 "ATLPages7Lib.DocumentProperties.1",
    _ 
    DTE.ActiveDocument _)  
    End Sub  
 
End Module  
```  
  
 Lorsque vous exécutez cette macro, la page de propriétés s’affichera indiquant le nom de fichier et l’état en lecture seule du document texte actif. L’état en lecture seule du document reflète uniquement la possibilité d’écrire dans le document dans l’environnement de développement ; Il n’affecte pas l’attribut en lecture seule du fichier sur disque.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés](../atl/atl-com-property-pages.md)   
 [Exemple ATLPages](../visual-cpp-samples.md)

