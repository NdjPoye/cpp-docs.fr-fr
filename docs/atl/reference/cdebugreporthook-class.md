---
title: Classe CDebugReportHook | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDebugReportHook
- CDebugReportHook
- ATL::CDebugReportHook
dev_langs:
- C++
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 632167d4f78ef930673450d6d087f32e91b6541f
ms.lasthandoff: 02/24/2017

---
# <a name="cdebugreporthook-class"></a>CDebugReportHook (classe)
Utilisez cette classe pour envoyer des rapports de débogage à un canal nommé.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|Appels [SetPipeName](#setpipename), [SetTimeout](#settimeout), et [SetHook](#sethook).|  
|[CDebugReportHook :: ~ CDebugReportHook](#dtor)|Appels [CDebugReportHook::RemoveHook](#removehook).|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(Statique) La fonction personnalisée qui est liée à la durée d’exécution C déboguer le processus de création de rapports.|  
|[CDebugReportHook::RemoveHook](#removehook)|Appelez cette méthode pour arrêter l’envoi de rapports de débogage pour le canal nommé et restaurer le raccordement de rapport précédente.|  
|[CDebugReportHook::SetHook](#sethook)|Appelez cette méthode pour commencer à envoyer des rapports de débogage pour le canal nommé.|  
|[CDebugReportHook::SetPipeName](#setpipename)|Appelez cette méthode pour définir l’ordinateur et le nom du canal auquel les rapports de débogage seront envoyés.|  
|[CDebugReportHook::SetTimeout](#settimeout)|Appelez cette méthode pour définir le délai en millisecondes d’attente de cette classe pour le canal nommé soit disponible.|  
  
## <a name="remarks"></a>Remarques  
 Créez une instance de cette classe dans les versions debug de vos services ou d’applications d’envoyer des rapports de débogage à un canal nommé. Débogage des rapports sont générés en appelant [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) ou à l’aide d’un wrapper pour cette fonction comme le [ATLTRACE](http://msdn.microsoft.com/library/c796baa5-e2b9-4814-a27d-d800590b102e) et [ATLASSERT ;](http://msdn.microsoft.com/library/98e3e0fc-77e2-499b-a6f6-b17a21c6fbd3) macros.  
  
 Utilisation de cette classe vous permet de déboguer interactivement les composants qui s’exécutent non interactif [stations window](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Notez que les rapports de débogage sont envoyés en utilisant le contexte de sécurité sous-jacente du thread. L’emprunt d’identité est temporairement désactivé afin que les rapports de débogage peuvent être affichés dans les situations où l’emprunt d’identité des utilisateurs de faibles privilèges est en cours, comme dans les applications web.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  
  
##  <a name="a-namecdebugreporthooka--cdebugreporthookcdebugreporthook"></a><a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook  
 Appels [SetPipeName](#setpipename), [SetTimeout](#settimeout), et [SetHook](#sethook).  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `szMachineName`  
 Le nom de l’ordinateur auquel la sortie de débogage doit être envoyée. Par défaut, l’ordinateur local.  
  
 `szPipeName`  
 Le nom du canal nommé dans lequel la sortie de débogage doit être envoyée.  
  
 `dwTimeout`  
 Durée en millisecondes d’attente de cette classe pour le canal nommé soit disponible.  
  
##  <a name="a-namedtora--cdebugreporthookcdebugreporthook"></a><a name="dtor"></a>CDebugReportHook :: ~ CDebugReportHook  
 Appels [CDebugReportHook::RemoveHook](#removehook).  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="a-namecdebugreporthookproca--cdebugreporthookcdebugreporthookproc"></a><a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc  
 La fonction personnalisée qui est liée à la durée d’exécution C déboguer le processus de création de rapports.  
  
```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `reportType`  
 Le type de rapport (_CRT_WARN, _CRT_ERROR ou _CRT_ASSERT).  
  
 `message`  
 La chaîne de message.  
  
 *returnValue*  
 La valeur qui doit être retournée par [_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne FALSE si le raccordement gère le message en question complètement afin qu’aucun rapport supplémentaire n’est requise. Retourne TRUE si `_CrtDbgReport` doit signaler le message de façon normale.  
  
### <a name="remarks"></a>Remarques  
 La fonction de création de rapports tente d’ouvrir le canal nommé et communiquer avec le processus à l’autre extrémité. Si le canal est occupé, la fonction de création de rapports attend que le canal est disponible ou l’expiration du délai. Le délai d’expiration peut être définie par le constructeur ou un appel à [CDebugReportHook::SetTimeout](#settimeout).  
  
 Le code de cette fonction est exécuté dans le contexte de sécurité sous-jacente du thread appelant, c'est-à-dire que l’emprunt d’identité est désactivé pour la durée de cette fonction.  
  
##  <a name="a-nameremovehooka--cdebugreporthookremovehook"></a><a name="removehook"></a>CDebugReportHook::RemoveHook  
 Appelez cette méthode pour arrêter l’envoi de rapports de débogage pour le canal nommé et restaurer le raccordement de rapport précédente.  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Appels [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) pour restaurer le raccordement de rapport précédente.  
  
##  <a name="a-namesethooka--cdebugreporthooksethook"></a><a name="sethook"></a>CDebugReportHook::SetHook  
 Appelez cette méthode pour commencer à envoyer des rapports de débogage pour le canal nommé.  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Appels [_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md) des rapports de débogage routés via [CDebugReportHookProc](#cdebugreporthookproc) au canal nommé. Cette classe effectue le suivi du raccordement de rapport précédente afin qu’il puisse être restaurées si [RemoveHook](#removehook) est appelée.  
  
##  <a name="a-namesetpipenamea--cdebugreporthooksetpipename"></a><a name="setpipename"></a>CDebugReportHook::SetPipeName  
 Appelez cette méthode pour définir l’ordinateur et le nom du canal auquel les rapports de débogage seront envoyés.  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `szMachineName`  
 Le nom de l’ordinateur auquel la sortie de débogage doit être envoyée.  
  
 `szPipeName`  
 Le nom du canal nommé dans lequel la sortie de débogage doit être envoyée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
##  <a name="a-namesettimeouta--cdebugreporthooksettimeout"></a><a name="settimeout"></a>CDebugReportHook::SetTimeout  
 Appelez cette méthode pour définir le délai en millisecondes d’attente de cette classe pour le canal nommé soit disponible.  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwTimeout`  
 Durée en millisecondes d’attente de cette classe pour le canal nommé soit disponible.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../atl/reference/atl-classes.md)

