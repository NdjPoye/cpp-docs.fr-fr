---
title: "_outp, _outpw, _outpd | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_outpd"
  - "_outp"
  - "_outpw"
apilocation: 
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_outpw"
  - "_outpd"
  - "_outp"
  - "outpd"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_outp (fonction)"
  - "_outpd (fonction)"
  - "_outpw (fonction)"
  - "octets, écrire sur des ports"
  - "mots doubles"
  - "mots doubles, écrire sur des ports"
  - "outp (fonction)"
  - "outpd (fonction)"
  - "outpw (fonction)"
  - "ports, écrire des octets à"
  - "mots"
  - "mots, écrire sur des ports"
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _outp, _outpw, _outpd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Produit sur un port un octet \(`_outp`\), un mot \(`_outpw`\), ou un mot double \(`_outpd`\).  
  
> [!IMPORTANT]
>  Ces fonctions sont obsolètes. Depuis Visual Studio 2015, elles ne sont pas disponibles dans la bibliothèque CRT.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
  
int _outp(unsigned short port,int databyte);unsigned short _outpw(unsigned short port,unsigned short dataword);unsigned long _outpd(unsigned short port,unsigned long dataword);  
```  
  
#### Paramètres  
 *port*  
 Numéro de port.  
  
 *databyte, dataword*  
 Valeurs de sortie.  
  
## Valeur de retour  
 Les fonctions retournent la sortie des données. Aucun retour d'erreur.  
  
## Notes  
 Les fonctions `_outp`, `_outpw` et `_outpd` écrivent respectivement un octet, un mot et un mot double sur le port de sortie spécifié. L’argument *port* peut être un entier non signé dans la plage 0 \- 65 535, *databyte* peut être un entier dans la plage 0 \- 255 et *dataword* peut être respectivement toute valeur de la plage d’un entier, un entier court non signé et un entier long non signé.  
  
 Comme ces fonctions écrivent directement sur un port d’E\/S, elles ne peuvent pas être utilisées dans du code utilisateur dans Windows NT, Windows 2000, Windows XP et Windows Server 2003. Pour plus d’informations sur l’utilisation des ports d’E\/S dans ces systèmes d’exploitation, recherchez « Communications série dans Win32 » sur MSDN.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_outp`|\<conio.h\>|  
|`_outpw`|\<conio.h\>|  
|`_outpd`|\<conio.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../c-runtime-library/crt-library-features.md).  
  
## Voir aussi  
 [Console et port E\/S](../c-runtime-library/console-and-port-i-o.md)   
 [\_inp, \_inpw, \_inpd](../c-runtime-library/inp-inpw-inpd.md)