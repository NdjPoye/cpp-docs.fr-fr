---
title: "CUrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CUrl"
  - "CUrl"
  - "ATL::CUrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUrl class"
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CUrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente une URL.  Elle vous permet de manipuler chaque élément de l'URL indépendamment des autres si l'analyse une chaîne existante d'URL ou de la génération d'une chaîne à partir de zéro.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CUrl  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CUrl::CUrl](../Topic/CUrl::CUrl.md)|Constructeur.|  
|[CUrl::~CUrl](../Topic/CUrl::~CUrl.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CUrl::Canonicalize](../Topic/CUrl::Canonicalize.md)|Appelez cette méthode pour convertir la chaîne d'URL au formulaire canonique.|  
|[CUrl::Clear](../Topic/CUrl::Clear.md)|Appelez cette méthode pour effacer tous les champs d'URL.|  
|[CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md)|Appelez cette méthode pour décoder et analyser l'URL.|  
|[CUrl::CreateUrl](../Topic/CUrl::CreateUrl.md)|Appelez cette méthode pour créer l'URL.|  
|[CUrl::GetExtraInfo](../Topic/CUrl::GetExtraInfo.md)|Appelez cette méthode pour obtenir des informations supplémentaires \(?*texte* ou \#text\) de l'URL.|  
|[CUrl::GetExtraInfoLength](../Topic/CUrl::GetExtraInfoLength.md)|Appelez cette méthode pour obtenir la longueur des informations supplémentaires \(?*texte* ou \#text\) à partir de l'URL.|  
|[CUrl::GetHostName](../Topic/CUrl::GetHostName.md)|Appelez cette méthode pour obtenir le nom d'hôte de l'URL.|  
|[CUrl::GetHostNameLength](../Topic/CUrl::GetHostNameLength.md)|Appelez cette méthode pour obtenir la longueur du nom d'hôte.|  
|[CUrl::GetPassword](../Topic/CUrl::GetPassword.md)|Appelez cette méthode pour obtenir le mot de passe de l'URL.|  
|[CUrl::GetPasswordLength](../Topic/CUrl::GetPasswordLength.md)|Appelez cette méthode pour obtenir la longueur du mot de passe.|  
|[CUrl::GetPortNumber](../Topic/CUrl::GetPortNumber.md)|Appelez cette méthode pour obtenir le numéro de port en termes de ATL\_URL\_PORT.|  
|[CUrl::GetScheme](../Topic/CUrl::GetScheme.md)|Appelez cette méthode pour obtenir le type d'URL.|  
|[CUrl::GetSchemeName](../Topic/CUrl::GetSchemeName.md)|Appelez cette méthode pour obtenir le nom de type d'URL.|  
|[CUrl::GetSchemeNameLength](../Topic/CUrl::GetSchemeNameLength.md)|Appelez cette méthode pour obtenir la longueur du nom de type d'URL.|  
|[CUrl::GetUrlLength](../Topic/CUrl::GetUrlLength.md)|Appelez cette méthode pour obtenir la longueur d'URL.|  
|[CUrl::GetUrlPath](../Topic/CUrl::GetUrlPath.md)|Appelez cette méthode pour obtenir le chemin d'accès de l'URL.|  
|[CUrl::GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md)|Appelez cette méthode pour obtenir la longueur de chemin d'accès de l'URL.|  
|[CUrl::GetUserName](../Topic/CUrl::GetUserName.md)|Appelez cette méthode pour obtenir le nom d'utilisateur de l'URL.|  
|[CUrl::GetUserNameLength](../Topic/CUrl::GetUserNameLength.md)|Appelez cette méthode pour obtenir la longueur du nom d'utilisateur.|  
|[CUrl::SetExtraInfo](../Topic/CUrl::SetExtraInfo.md)|Appelez cette méthode pour définir des informations supplémentaires \(?*texte* ou \#text\) de l'URL.|  
|[CUrl::SetHostName](../Topic/CUrl::SetHostName.md)|Appelez cette méthode pour définir le nom d'hôte.|  
|[CUrl::SetPassword](../Topic/CUrl::SetPassword.md)|Appelez cette méthode pour définir le mot de passe.|  
|[CUrl::SetPortNumber](../Topic/CUrl::SetPortNumber.md)|Appelez cette méthode pour définir le numéro de port en termes de ATL\_URL\_PORT.|  
|[CUrl::SetScheme](../Topic/CUrl::SetScheme.md)|Appelez cette méthode pour définir le type d'URL.|  
|[CUrl::SetSchemeName](../Topic/CUrl::SetSchemeName.md)|Appelez cette méthode pour définir le nom de type d'URL.|  
|[CUrl::SetUrlPath](../Topic/CUrl::SetUrlPath.md)|Appelez cette méthode pour définir le chemin d'accès de l'URL.|  
|[CUrl::SetUserName](../Topic/CUrl::SetUserName.md)|Appelez cette méthode pour définir le nom d'utilisateur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CUrl::operator \=](../Topic/CUrl::operator%20=.md)|Assigne l'objet spécifié d' `CUrl` à l'objet actuel d' `CUrl` .|  
  
## Notes  
 `CUrl` vous permet de manipuler les champs d'une URL, tels que le chemin ou le numéro de port.  `CUrl` inclut l'URL de la forme suivante :  
  
 \<Scheme\>: \/\<UserName\>:\<Password\>@\<HostName\>:\<PortNumber\>\/\<UrlPath\>\<ExtraInfo\>  
  
 \(Certains champs sont facultatifs.\) Par exemple, considérez cette URL :  
  
 http:\/\/someone:secret@www.microsoft.com:80\/visualc\/stuff.htm\#contents  
  
 [CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md) l'analyse comme suit :  
  
-   Modèle : « http » ou [ATL\_URL\_SCHEME\_HTTP](../Topic/ATL_URL_SCHEME.md)  
  
-   Nom d'utilisateur : « quelqu'un »  
  
-   Mot de passe : « secret »  
  
-   Hostname : « www.microsoft.com »  
  
-   Numéro de port : 80  
  
-   UrlPath : « visualc\/stuff.htm »  
  
-   ExtraInfo : « \#contents »  
  
 Pour manipuler le champ d'UrlPath \(par exemple\), vous utiliserez [GetUrlPath](../Topic/CUrl::GetUrlPath.md), [GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md), et [SetUrlPath](../Topic/CUrl::SetUrlPath.md).  Vous utiliserez [CreateUrl](../Topic/CUrl::CreateUrl.md) pour créer la chaîne complète d'URL.  
  
## Configuration requise  
 **Header:** atlutil.h  
  
## Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)