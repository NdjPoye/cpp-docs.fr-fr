---
title: "Cloud et programmation Web dans Visual C++ | Microsoft Docs"
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
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
caps.latest.revision: 13
caps.handback.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Cloud et programmation Web dans Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En C\+\+, vous disposez de plusieurs options de connexion web et cloud.  
  
 [Microsoft Azure Mobile Services](http://www.windowsazure.com/develop/mobile/)  
 Fournit des API natives que vous pouvez utiliser dans les applications du Windows Store ou les applications de bureau Windows pour vous connecter à Windows Azure Mobile Services. Bien que la plupart des exemples présentés sur le site web soient en C\#, vous pouvez aussi utiliser C\+\+. Pour plus d’informations, consultez [Démarrage rapide : ajout d’un service mobile en C\+\+](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx).  
  
 [Interface Live REST](http://msdn.microsoft.com/library/live/hh243648.aspx)  
 Fournit des points de terminaison REST que vous pouvez utiliser dans les applications du Windows Store, les applications de bureau Windows ou les applications Linux C\+\+ pour vous connecter aux services [Live](http://msdn.microsoft.com/live/ff519582), tels que SkyDrive, Outlook.com et Skype. Au lieu de parcourir le Kit de développement logiciel \(SDK\) Live, qui concerne uniquement les applications .NET, les applications C\+\+ utilisent directement ces points de terminaison.  
  
 [C\+\+ REST SDK \(Codename "Casablanca"\)](../top/cpp-rest-sdk-codename-casablanca.md)  
 Fournit des méthodes de wrapper HTTP asynchrones pratiques qui ont été conçues pour assurer une compatibilité multiplateforme et être utilisées dans les applications de bureau sur des systèmes d'exploitation Windows 7 et Windows Server 2012. Vous pouvez aussi les utiliser dans les applications de plateforme Windows universelle. Toutefois, pour les applications qui ne ciblent que la plateforme Windows universelle, nous vous recommandons d’utiliser la classe `Windows::Web:HttpClient`. Le Kit de développement logiciel \(SDK\) C\+\+ REST \(nom de code « Casablanca »\) propose aussi des classes d'assistance qui prennent en charge les appels REST et convertissent les données JSON en types C\+\+. Le Kit de développement logiciel \(SDK\) est disponible sur [CodePlex](http://casablanca.codeplex.com/) et contient des exemples de fichiers tels que [live\_connect.h](http://casablanca.codeplex.com/SourceControl/latest#Release/collateral/Samples/WindowsLiveAuth/live_connect.h), qui fournit des méthodes d’assistance pour la connexion aux services [Live](http://msdn.microsoft.com/live/ff519582).  
  
 [Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)  
 Classe de client HTTP Windows Runtime modélisée sur la classe .NET Framework du même nom dans l'espace de noms System.Web.`HttpClient` prend entièrement en charge le chargement et le téléchargement asynchrones via HTTP, ainsi que les filtres de pipeline qui permettent l'insertion de gestionnaires HTTP personnalisés dans le pipeline. Le Kit de développement logiciel \(SDK\) Windows inclut des exemples de filtres pour les connexions réseau limitées, l'authentification OAuth et bien plus encore.  
  
 [Interface IXMLHTTPRequest2](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)  
 Fournit une interface COM native que vous pouvez utiliser dans les applications du Windows Store ou les applications de bureau Windows pour vous connecter à Internet via HTTP et émettre GET, PUT et d'autres commandes HTTP. Pour plus d'informations, consultez [Procédure pas à pas : connexion à l’aide de tâches et de requêtes HTTP XML](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md).  
  
 [Windows Internet \(WinInet\)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)  
 API Windows que vous pouvez utiliser dans les applications de bureau Windows pour vous connecter à Internet.  
  
## Voir aussi  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)   
 [Connexion aux réseaux et aux services web \(applications du Windows Store en C\#\/VB\/C\+\+ et XAML\)](http://msdn.microsoft.com/library/windows/apps/br229573.aspx)