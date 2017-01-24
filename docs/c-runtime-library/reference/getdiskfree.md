---
title: "_getdiskfree | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getdiskfree"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "getdiskfree"
  - "_getdiskfree"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_diskfree_t (type)"
  - "_getdiskfree (fonction)"
  - "taille de disque"
  - "diskfree_t (type)"
  - "getdiskfree (fonction)"
ms.assetid: 47a3f6cf-4816-452a-8f3d-1c3ae02a0f2a
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getdiskfree
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilise les informations relatives à un lecteur de disque pour remplir une structure `_diskfree_t`.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, voir [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
unsigned _getdiskfree(  
   unsigned drive,  
   struct _diskfree_t * driveinfo  
);  
```  
  
#### Paramètres  
 \[in\] `drive`  
 Lecteur de disque pour lequel vous voulez obtenir des informations.  
  
 \[out\] `driveinfo`  
 Structure `_diskfree_t` qui sera remplie avec les informations sur le lecteur.  
  
## Valeur de retour  
 Si la fonction aboutit, la valeur de retour est égale à zéro.  Si la fonction échoue, la valeur de retour est le code d'erreur.  La valeur `errno` est définie pour les erreurs retournées par le système d'exploitation.  Pour plus d'informations sur les conditions d'erreur indiquées par `errno`, consultez [errno, constantes](../../c-runtime-library/errno-constants.md).  
  
## Notes  
 La structure `_diskfree_t` est définie dans Direct.h.  
  
```  
struct _diskfree_t {   
   unsigned total_clusters;   
   unsigned avail_clusters;   
   unsigned sectors_per_cluster;   
   unsigned bytes_per_sector;   
};  
```  
  
 Cette fonction valide ses paramètres.  Si le pointeur `driveinfo` a la valeur `NULL` ou que `drive` spécifie un lecteur non valide, cette fonction appelle un gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à continuer, cette fonction retourne `EINVAL` et définit à `errno` à `EINVAL`.  Plage de lecteurs valide de 0 à 26.  Avec la valeur 0, `drive` désigne le lecteur actif ; après quoi, les nombres sont mappés aux lettres de l'alphabet anglais, si bien que 1 indique le lecteur A, 3 le lecteur C, etc.  
  
 `total_clusters`  
 Nombre total de clusters utilisés et disponibles sur le disque.  
  
 `avail_clusters`  
 Nombre de clusters non utilisés sur le disque.  
  
 `sectors_per_cluster`  
 Nombre de secteurs dans chaque cluster.  
  
 `bytes_per_sector`  
 Taille de chaque secteur en octets.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getdiskfree`|\<direct.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_getdiskfree.c  
// compile with: /c  
#include <windows.h>  
#include <direct.h>  
#include <stdio.h>  
#include <tchar.h>  
  
TCHAR   g_szBorder[] = _T("======================================================================\n");  
TCHAR   g_szTitle1[] = _T("|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|\n");  
TCHAR   g_szTitle2[] = _T("|=====|==============|==============|=================|==============|\n");  
TCHAR   g_szLine[]   = _T("|  A: |              |              |                 |              |\n");  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal);  
  
int main(int argc, char* argv[]) {  
   TCHAR szMsg[4200];  
   struct _diskfree_t df = {0};  
   ULONG uDriveMask = _getdrives();  
   unsigned uErr, uLen, uDrive;  
  
   printf(g_szBorder);  
   printf(g_szTitle1);  
   printf(g_szTitle2);  
  
   for (uDrive=1; uDrive<=26; ++uDrive) {  
      if (uDriveMask & 1) {  
         uErr = _getdiskfree(uDrive, &df);  
         memcpy(szMsg, g_szLine, sizeof(g_szLine));  
         szMsg[3] = uDrive + 'A' - 1;  
  
         if (uErr == 0) {  
            utoiRightJustified(szMsg+8,  szMsg+19, df.total_clusters);  
            utoiRightJustified(szMsg+23, szMsg+34, df.avail_clusters);  
            utoiRightJustified(szMsg+38, szMsg+52, df.sectors_per_cluster);  
            utoiRightJustified(szMsg+56, szMsg+67, df.bytes_per_sector);  
         }  
         else {  
            uLen = FormatMessage(FORMAT_MESSAGE_FROM_SYSTEM, NULL,  
                            uErr, 0, szMsg+8, 4100, NULL);  
            szMsg[uLen+6] = ' ';  
            szMsg[uLen+7] = ' ';  
            szMsg[uLen+8] = ' ';  
         }  
  
         printf(szMsg);  
      }  
  
      uDriveMask >>= 1;  
   }  
  
   printf(g_szBorder);  
}  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal) {  
   TCHAR* szCur = szRight;  
   int nComma = 0;  
  
   if (uVal) {  
      while (uVal && (szCur >= szLeft)) {  
         if   (nComma == 3) {  
            *szCur = ',';  
            nComma = 0;  
         }  
         else {  
            *szCur = (uVal % 10) | 0x30;  
            uVal /= 10;  
            ++nComma;  
         }  
  
         --szCur;  
      }  
   }  
   else {  
      *szCur = '0';  
      --szCur;  
   }  
  
   if (uVal) {  
      szCur = szLeft;  
  
      while   (szCur <= szRight) {  
         *szCur = '*';  
         ++szCur;  
      }  
   }  
}  
```  
  
  **\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=**  
**&#124;DRIVE&#124;TOTAL CLUSTERS&#124;AVAIL CLUSTERS&#124;SECTORS \/ CLUSTER&#124;BYTES \/ SECTOR&#124;**  
**&#124;\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;\=\=\=\=\=\=\=\=\=\=\=\=\=\=&#124;**  
**&#124;  A: &#124; The device is not ready.  &#124;                 &#124;              &#124;**  
**&#124;  C: &#124;    4,721,093 &#124;    3,778,303 &#124;               8 &#124;          512 &#124;**  
**&#124;  D: &#124;    1,956,097 &#124;    1,800,761 &#124;               8 &#124;          512 &#124;**  
**&#124;  E: &#124; The device is not ready.  &#124;                 &#124;              &#124;**  
**\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=\=**    
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)