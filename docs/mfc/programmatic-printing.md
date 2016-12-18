---
title: "Impression par programmation | Microsoft Docs"
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
  - "documents actifs (C++), imprimer"
  - "IPrint (interface)"
  - "imprimer (MFC)"
  - "imprimer (MFC), documents actifs"
  - "imprimer (MFC), programmation"
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impression par programmation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE a fourni les moyens d'identifier des documents persistants \(**GetClassFile**\) et de les charger dans leur code associé \(`CoCreateInstance`, **QueryInterface\(IID\_IPersistFile\)**, **QueryInterface\(IID\_IPersistStorage\)**, **IPersistFile::Load**, et **IPersistStorage::Load**\).  Pour activer davantage l'impression de documents, la relation contenant\-contenu de document actif \(en utilisant une conception OLE existante non fournie avec OLE 2.0 à l'origine\) présente une interface standard de base d'impression, `IPrint`, généralement disponible via un objet qui peut charger l'état permanent du type de document.  Chaque vue d'un document actif peut éventuellement prendre en charge l'interface **IPrint** pour fournir ces fonctions.  
  
 L'interface `IPrint` se définit de la manière suivante :  
  
 `interface IPrint : IUnknown`  
  
 `{`  
  
 `HRESULT SetInitialPageNum([in] LONG nFirstPage);`  
  
 `HRESULT GetPageInfo(`  
  
 `[out] LONG *pnFirstPage,`  
  
 `[out] LONG *pcPages);`  
  
 `HRESULT Print(`  
  
 `[in] DWORD grfFlags,`  
  
 `[in,out] DVTARGETDEVICE **pptd,`  
  
 `[in,out] PAGESET ** ppPageSet,`  
  
 `[in,out] STGMEDIUM **ppstgmOptions,`  
  
 `[in] IContinueCallback* pCallback,`  
  
 `[in] LONG nFirstPage,`  
  
 `[out] LONG *pcPagesPrinted,`  
  
 `[out] LONG *pnPageLast);`  
  
 `};`  
  
 Les clients et conteneurs utilisent simplement **IPrint::Print** pour demander au document de s'imprimer une fois qu'il est chargé, en spécifiant les balises de paramètre général de présentation, le périphérique cible, les pages à imprimer, et les options supplémentaires.  Le client peut également contrôler la suite de l'impression via l'interface `IContinueCallback` \(voir ci\-dessous\).  
  
 En outre, **IPrint::SetInitialPageNum** prend en charge la capacité d'afficher une série de documents en un seul en comptant les pages sans problème, ce qui est évidemment un avantage pour les conteneurs de documents actifs tels que le classeur Office.  **IPrint::GetPageInfo** rend l'affichage des informations de pagination simple en permettant à l'appelant de récupérer le numéro de page de démarrage précédemment passé à **SetInitialPageNum** \(ou le numéro de page de démarrage interne par défaut du document\) et le nombre de pages dans le document.  
  
 Les objets prenant en charge `IPrint` sont marqués dans le Registre avec la clé « Printable » stockée sous le CLSID de l'objet :  
  
 HKEY\_CLASSES\_ROOT\\CLSID\\{...}\\Printable  
  
 `IPrint` est généralement implémentée sur le même objet qui prend en charge `IPersistFile` ou `IPersistStorage`.  Les appelants notent la possibilité d'imprimer de façon programmée l'état permanent d'une certaine classe en consultant le Registre pour la clé « Printable ».  Actuellement, « Printable » indique la prise en charge d'au moins `IPrint`; d'autres interfaces peuvent être définies ultérieurement qui seront ensuite accessibles à partir de `QueryInterface` où **IPrint** représente simplement le niveau de base de la prise en charge.  
  
 Pendant la procédure d'impression, vous pouvez souhaiter que le client ou le conteneur à l'origine de l'impression puisse contrôler si l'impression doit continuer.  Par exemple, le conteneur peut prendre en charge une commande "Arrêt d'impression" qui doit arrêter le travail d'impression dès que possible.  Pour prendre en charge cette fonctionnalité, le client d'un objet imprimable peut implémenter un petit objet attracteur de notification avec l'interface `IContinueCallback`:  
  
 `interface IContinueCallback : IUnknown`  
  
 `{`  
  
 `HRESULT FContinue(void);`  
  
 `HRESULT FContinuePrinting(`  
  
 `[in] LONG cPagesPrinted,`  
  
 `[in] LONG nCurrentPage,`  
  
 `[in] LPOLESTR pszPrintStatus);`  
  
 `};`  
  
 Cette interface est conçue pour être utile en tant que fonction de rappel de suite générique qui remplace des procédures de suite dans l'API Win32 \(par exemple **AbortProc** pour l'impression et **EnumMetafileProc** pour l'énumération de métafichier\).  Cette conception de l'interface est utile dans une grande variété de processus longs.  
  
 Dans les cas les plus génériques, la fonction **IContinueCallback::FContinue** est appelée régulièrement par tout processus long.  L'objet attracteur retourne `S_OK` pour continuer l'opération, et **S\_FALSE** pour arrêter la procédure dès que possible.  
  
 **FContinue**; toutefois, n'est pas utilisé dans le contexte de **IPrint::Print**; en revanche, l'impression utilise **IContinueCallback::FContinuePrint**.  Tout objet d'impression doit appeler régulièrement **FContinuePrinting** en lui transmettant le nombre de pages qui ont été imprimées, le numéro de la page en cours d'impression, et une chaîne supplémentaire qui décrit l'état d'impression que le client peut choisir d'afficher à l'utilisateur \(par exemple "page 5 sur 19"\).  
  
## Voir aussi  
 [Conteneurs de documents actifs](../mfc/active-document-containers.md)