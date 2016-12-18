---
title: "Cr&#233;ation d&#39;une application MFC de style navigateur Web | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcweb.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, applications Web"
  - "applications Web, créer"
  - "navigateurs Web"
  - "navigateurs Web, créer à partir d'une architecture MFC"
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;une application MFC de style navigateur Web
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une application de style navigateur Web permet d'accéder à des informations d'Internet \(documents HTML ou documents actifs\) ou d'un intranet, ainsi qu'à des dossiers figurant dans un système de fichiers local ou sur un réseau.  En dérivant la classe d'affichage de l'application de la classe [CHtmlView](../../mfc/reference/chtmlview-class.md), vous transformez de manière efficace l'application en navigateur Web, en dotant la vue du contrôle WebBrowser.  
  
### Pour créer une application de style navigateur Web basée sur l'architecture Document\/Vue MFC  
  
1.  Suivez les instructions indiquées dans [Création d'une application MFC](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Dans la page [Type d'application](../../mfc/reference/application-type-mfc-application-wizard.md) de l'Assistant Application MFC, vérifiez que la case à cocher **Prise en charge de l'architecture Document\/Vue** est activée. \(Vous pouvez choisir **Monodocument \(SDI\)** ou **Multidocument \(MDI\)**, mais pas **Basée sur des boîtes de dialogue**.\)  
  
3.  Dans la page [Consultation des classes générées](../../mfc/reference/generated-classes-mfc-application-wizard.md), utilisez le menu déroulant **Classe de base** pour sélectionner `CHtmlView`.  
  
4.  Sélectionnez les éventuelles autres options que vous voulez intégrer dans l'application squelette.  
  
5.  Cliquez sur **Terminer**.  
  
 Le contrôle WebBrowser prend en charge l'exploration Web par le biais des liens hypertexte et de la navigation dans les URL \(Uniform Resource Locator\).  Le contrôle conserve un historique qui permet à l'utilisateur de revenir sur les sites, dossiers et documents précédemment explorés.  Le contrôle gère directement la navigation, les liens hypertexte, les historiques, les favoris et la sécurité.  Les applications peuvent utiliser le contrôle WebBrowser en tant que conteneur de documents actifs pour héberger également les documents actifs.  Il est ainsi possible d'ouvrir et de modifier sur place des documents dotés d'une mise en forme enrichie, tels que des feuilles de calculs Microsoft Excel ou des documents Word, à partir du contrôle WebBrowser.  Le contrôle WebBrowser constitue également un conteneur de contrôles ActiveX permettant d'héberger n'importe quel contrôle ActiveX.  
  
> [!NOTE]
>  Le contrôle ActiveX WebBrowser \(et par conséquent la classe `CHtmlView`\) n'est disponible que pour les applications s'exécutant sous les versions de Windows pour lesquelles Internet Explorer 4.0 ou version ultérieure a été installé.  
  
 Dans la mesure où la classe `CHtmlView` implémente simplement le contrôle Web browser Microsoft, sa prise en charge de l'impression est différente de celle des autres classes dérivées de [CView](../../mfc/reference/cview-class.md).  Le contrôle WebBrowser implémente plus exactement l'interface utilisateur de l'imprimante et l'impression.  En conséquence, la classe `CHtmlView` ne prend pas en charge l'aperçu avant impression et l'infrastructure ne propose pas d'autres fonctions de prise en charge de l'impression, comme [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md), [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md) et [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md), qui sont disponibles dans d'autres applications MFC.  
  
 La classe `CHtmlView` joue le rôle d'un wrapper pour le contrôle Web browser, qui dote votre application d'une vue sur une page Web ou HTML.  L'Assistant crée une substitution de la fonction [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) dans la classe d'affichage, proposant un lien de navigation vers le site Web Microsoft Visual C\+\+ :  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),NULL,NULL);  
}  
```  
  
 Vous pouvez remplacer ce site par un des vôtres ou vous pouvez utiliser la fonction membre [LoadFromResource](../Topic/CHtmlView::LoadFromResource.md) pour ouvrir une page HTML qui réside dans le script de ressources du projet en tant que contenu par défaut pour la vue.  Par exemple :  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   LoadFromResource(IDR_HTML1);  
}  
```  
  
## Voir aussi  
 [MFC Sample MFCIE](http://msdn.microsoft.com/fr-fr/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)   
 [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md)   
 [Pages de propriétés](../../ide/property-pages-visual-cpp.md)   
 [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md)   
 [Deploying Applications](http://msdn.microsoft.com/fr-fr/4ff8881d-0daf-47e7-bfe7-774c625031b4)