---
title: Création d’une Application MFC de Style navigateur Web | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20c7228b08200466bd62d1cdbbf7e2f66f8efebb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-web-browser-style-mfc-application"></a>Création d'une application MFC de style navigateur Web
Une application de style navigateur Web peut accéder aux informations à partir d’Internet (tels que HTML ou documents actifs) ou un intranet, ainsi que des dossiers du système de fichiers local et sur un réseau. En dérivant la classe d’affichage de l’application de [CHtmlView](../../mfc/reference/chtmlview-class.md)et vous rendre à l’application un navigateur Web en fournissant l’affichage avec le contrôle WebBrowser.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>Pour créer une application de navigateur Web basée sur l’architecture document/vue MFC  
  
1.  Suivez les instructions de [création d’une Application MFC](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Dans l’Assistant Application MFC [Type d’Application](../../mfc/reference/application-type-mfc-application-wizard.md) page, assurez-vous que le **architecture Document/vue** est activée. (Vous pouvez choisir le **document unique** ou **plusieurs documents**, mais pas **basée sur un dialogue**.)  
  
3.  Sur le [Classes générées](../../mfc/reference/generated-classes-mfc-application-wizard.md) page, utilisez la **classe de Base** menu déroulant pour sélectionner `CHtmlView`.  
  
4.  Sélectionnez d’autres options intégrées à l’application squelette.  
  
5.  Cliquez sur **Terminer**.  
  
 Le contrôle WebBrowser prend en charge la navigation sur le Web par le biais des liens hypertexte et de navigation de la protection continue des données (URL, Uniform Resource Locator). Le contrôle gère une liste de l’historique qui permet à l’utilisateur naviguer vers l’avant et vers l’arrière dans précédemment parcourues sites, des dossiers et des documents. Le contrôle gère directement la navigation, des liens hypertexte, les listes de l’historique, Favoris et la sécurité. Applications peuvent utiliser le contrôle WebBrowser en tant que conteneur de documents actifs pour héberger également des documents active. Par conséquent, les documents enrichis telles que feuilles de calcul Microsoft Excel ou Word pour pouvoir ouvrir et modifié sur place à partir du contrôle WebBrowser. Le contrôle WebBrowser est également un conteneur de contrôles ActiveX qui peut héberger un contrôle ActiveX.  
  
> [!NOTE]
>  Le contrôle WebBrowser ActiveX (et par conséquent `CHtmlView`) est disponible uniquement pour les applications qui s’exécutent sous les versions de Windows dans lesquelles Internet Explorer 4.0 ou version ultérieure a été installé.  
  
 Étant donné que `CHtmlView` implémente simplement le contrôle de navigateur Web Microsoft, sa prise en charge pour l’impression n’est pas comme les autres [CView](../../mfc/reference/cview-class.md)-classes dérivées. Au lieu de cela, le contrôle WebBrowser implémente l’interface utilisateur de l’imprimante et l’impression. Par conséquent, `CHtmlView` est pas prise en charge l’aperçu avant impression, et le framework ne fournit pas d’autres fonctions de prise en charge l’impression : par exemple, [comme CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), et [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), qui sont disponible dans d’autres applications MFC.  
  
 `CHtmlView` sert de wrapper pour le contrôle de navigateur Web, ce qui donne une vue sur un site Web ou une page HTML à votre application. L’Assistant crée une substitution de la [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) fonction dans la classe d’affichage, en fournissant un lien de navigation vers le site Web de Microsoft Visual C++ :  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
    NULL,
    NULL);

} 
```  
  
 Vous pouvez remplacer ce site par celle de votre choix, ou vous pouvez utiliser la [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) fonction membre pour ouvrir une page HTML qui réside dans le script de ressources du projet en tant que le contenu par défaut pour la vue. Par exemple :  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    LoadFromResource(IDR_HTML1);

} 
```  
  
## <a name="see-also"></a>Voir aussi  
 [MFC, exemple MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)   
 [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md)   
 [Pages de propriétés](../../ide/property-pages-visual-cpp.md)   
 [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md)   
 [Déploiement d’Applications](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

