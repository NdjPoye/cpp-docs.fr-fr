---
title: "Date et heure&#160;: prise en charge SYSTEMTIME | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "heure système"
  - "FILETIME (structure), avec la classe CTime"
  - "heure (C++), mise en forme"
  - "SYSTEMTIME (structure)"
  - "dates (C++), MFC"
  - "heure, de mise en forme (C++)"
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Date et heure&#160;: prise en charge SYSTEMTIME
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le [CTime](../atl-mfc-shared/reference/ctime-class.md) classe a des constructeurs qui acceptent les heures système et fichier provenant de Win32. Si vous utilisez des objets `CTime` à cette fin, vous devez modifier leur initialisation en conséquence, comme expliqué dans cet article.  
  
 Pour plus d’informations sur la structure SYSTEMTIME, consultez [SYSTEMTIME](../mfc/reference/systemtime-structure1.md). Pour plus d’informations sur la structure FILETIME, consultez [FILETIME](../mfc/reference/filetime-structure.md).  
  
 MFC fournit toujours des constructeurs `CTime` qui prennent des arguments de date/heure dans le style MS-DOS mais, depuis MFC version 3.0, la classe `CTime` prend aussi en charge un constructeur qui utilise une structure `SYSTEMTIME` Win32 et un autre constructeur qui utilise une structure `FILETIME` Win32.  
  
 Les nouveaux constructeurs `CTime` sont :  
  
-   CTime (const SYSTEMTIME & `sysTime`) ;  
  
-   CTime (const FILETIME & `fileTime`) ;  
  
 Le paramètre `fileTime` est une référence à une structure `FILETIME` Win32, qui représente la date/heure comme une valeur sur 64 bits, qui est un format plus pratique pour le stockage interne qu'une structure `SYSTEMTIME` et le format utilisé par Win32 pour représenter la date/heure de création d'un fichier.  
  
 Si votre code contient un objet `CTime` initialisé avec la date/heure système, vous devez utiliser le constructeur `SYSTEMTIME` de Win32.  
  
 Vous aurez probablement n’utilisez pas `CTime` `FILETIME` directement l’initialisation. Si vous utilisez un `CFile` objet pour manipuler un fichier, [CFile::GetStatus](../mfc/reference/cfile-class.md#getstatus) récupère l’horodatage de fichier pour vous via un `CTime` objet initialisé avec un `FILETIME` structure.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Quelle action voulez-vous en savoir plus  
  
-   [Générale programmation date et heure dans MFC](../atl-mfc-shared/date-and-time.md)  
  
-   [Prise en charge de l’Automation de programmation date et heure](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [Classes à but général pour la programmation de l’heure et de date](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Date et heure](../atl-mfc-shared/date-and-time.md)

