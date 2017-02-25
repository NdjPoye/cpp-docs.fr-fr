---
title: "/CLRSUPPORTLASTERROR (Conserver le dernier code d&#39;erreur pour les appels PInvoke) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRSUPPORTLASTERROR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRSUPPORTLASTERROR (option de l'éditeur de liens)"
  - "-CLRSUPPORTLASTERROR (option de l'éditeur de liens)"
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /CLRSUPPORTLASTERROR (Conserver le dernier code d&#39;erreur pour les appels PInvoke)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option **\/CLRSUPPORTLASTERROR**, qui est activée par défaut, conserve le dernier code d'erreur des fonctions appelées à l'aide du mécanisme P\/Invoke, ce qui vous permet d'appeler des fonctions natives dans des DLL, à partir de code compilé avec **\/clr**.  
  
## Syntaxe  
  
```  
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}  
```  
  
## Notes  
 La conservation du dernier code d'erreur implique une réduction des performances.  Si vous ne souhaitez pas subir l'impact sur les performances de la conservation du dernier code d'erreur, liez avec **\/CLRSUPPORTLASTERROR:NO**.  
  
 Vous pouvez réduire l'impact sur les performances en liant avec **\/CLRSUPPORTLASTERROR:SYSTEMDLL** ; en effet, cette option ne conserve que le dernier code d'erreur des fonctions contenues dans des DLL système.  Une DLL système est définie comme l'une des suivantes :  
  
|||||  
|-|-|-|-|  
|ACLUI.DLL|ACTIVEDS.DLL|ADPTIF.DLL|ADVAPI32.DLL|  
|ASYCFILT.DLL|AUTHZ.DLL|AVICAP32.DLL|AVIFIL32.DLL|  
|CABINET.DLL|CLUSAPI.DLL|COMCTL32.DLL|COMDLG32.DLL|  
|COMSVCS.DLL|CREDUI.DLL|CRYPT32.DLL|CRYPTNET.DLL|  
|CRYPTUI.DLL|D3D8THK.DLL|DBGENG.DLL|DBGHELP.DLL|  
|DCIMAN32.DLL|DNSAPI.DLL|DSPROP.DLL|DSUIEXT.DLL|  
|GDI32.DLL|GLU32.DLL|HLINK.DLL|ICM32.DLL|  
|IMAGEHLP.DLL|IMM32.DLL|IPHLPAPI.DLL|IPROP.DLL|  
|KERNEL32.DLL|KSUSER.DLL|LOADPERF.DLL|LZ32.DLL|  
|MAPI32.DLL|MGMTAPI.DLL|MOBSYNC.DLL|MPR.DLL|  
|MPRAPI.DLL|MQRT.DLL|MSACM32.DLL|MSCMS.DLL|  
|MSI.DLL|MSIMG32.DLL|MSRATING.DLL|MSTASK.DLL|  
|MSVFW32.DLL|MSWSOCK.DLL|MTXEX.DLL|NDDEAPI.DLL|  
|NETAPI32.DLL|NPPTOOLS.DLL|NTDSAPI.DLL|NTDSBCLI.DLL|  
|NTMSAPI.DLL|ODBC32.DLL|ODBCBCP.DLL|OLE32.DLL|  
|OLEACC.DLL|OLEAUT32.DLL|OLEDLG.DLL|OPENGL32.DLL|  
|PDH.DLL|POWRPROF.DLL|QOSNAME.DLL|QUERY.DLL|  
|RASAPI32.DLL|RASDLG.DLL|RASSAPI.DLL|RESUTILS.DLL|  
|RICHED20.DLL|RPCNS4.DLL|RPCRT4.DLL|RTM.DLL|  
|RTUTILS.DLL|SCARDDLG.DLL|SECUR32.DLL|SENSAPI.DLL|  
|SETUPAPI.DLL|SFC.DLL|SHELL32.DLL|SHFOLDER.DLL|  
|SHLWAPI.DLL|SISBKUP.DLL|SNMPAPI.DLL|SRCLIENT.DLL|  
|STI.DLL|TAPI32.DLL|TRAFFIC.DLL|URL.DLL|  
|URLMON.DLL|USER32.DLL|USERENV.DLL|USP10.DLL|  
|UXTHEME.DLL|VDMDBG.DLL|VERSION.DLL|WINFAX.DLL|  
|WINHTTP.DLL|WININET.DLL|WINMM.DLL|WINSCARD.DLL|  
|WINTRUST.DLL|WLDAP32.DLL|WOW32.DLL|WS2\_32.DLL|  
|WSNMP32.DLL|WSOCK32.DLL|WTSAPI32.DLL|XOLEHLP.DLL|  
  
> [!NOTE]
>  La conservation de la dernière erreur n'est pas prise en charge pour les fonctions non managées utilisées par du code CLR dans le même module.  
  
-   Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Exemple  
 L'exemple suivant définit une DLL native avec une fonction exportée qui modifie la dernière erreur.  
  
```  
// CLRSUPPORTLASTERROR_dll.cpp  
// compile with: /LD  
#include <windows.h>  
#include <math.h>  
  
#pragma unmanaged  
__declspec(dllexport) double MySqrt(__int64 n) {  
   SetLastError(DWORD(-1));  
   return sqrt(double(n));  
}  
```  
  
## Exemple  
 L'exemple suivant utilise la DLL et illustre l'utilisation de **\/CLRSUPPORTLASTERROR**.  
  
```  
// CLRSUPPORTLASTERROR_client.cpp  
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll  
// processor: x86  
#include <windows.h>  
#include <wininet.h>  
#include <stdio.h>  
#include <math.h>  
  
#pragma comment(lib, "wininet.lib")  
  
double MySqrt(__int64 n);  
  
#pragma managed  
int main() {  
   double   d = 0.0;  
   __int64 n = 65;  
   HANDLE  hGroup = NULL;  
   GROUPID groupID;  
   DWORD   dwSet = 127, dwGet = 37;  
  
   SetLastError(dwSet);  
   d = MySqrt(n);  
   dwGet = GetLastError();  
  
   if (dwGet == DWORD(-1))  
      printf_s("GetLastError for application call succeeded (%d).\n",  
             dwGet);  
   else  
      printf_s("GetLastError for application call failed (%d).\n",  
             dwGet);  
  
   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,  
                           0, 0, &groupID, 0);  
   dwGet = GetLastError();  
   if (dwGet == 183)  
      printf_s("GetLastError for system call succeeded (%d).\n",  
             dwGet);  
   else  
      printf_s("GetLastError for system call failed (%d).\n",  
             dwGet);  
}  
```  
  
  **GetLastError pour l'appel d'application échoué \(127\).**  
**GetLastError pour l'appel système réussi \(183\).**   
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)