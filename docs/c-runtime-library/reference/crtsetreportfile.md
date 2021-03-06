---
title: _CrtSetReportFile | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetReportFile
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- CrtSetReportFile
- _CrtSetReportFile
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3df4f54ad8e191dac7110a914bdde1cec888ff9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402333"
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

在使用后[_CrtSetReportMode](crtsetreportmode.md)指定 **_CRTDBG_MODE_FILE**，你可以指定要接收的消息文本的文件句柄。 **_CrtSetReportFile**也使用[_CrtDbgReport、 _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)指定的文本 （仅限调试版本） 的目标位置。

## <a name="syntax"></a>语法

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>参数

*reportType*<br/>
报告类型： **_CRT_WARN**， **_CRT_ERROR**，和 **_CRT_ASSERT**。

*reportFile*<br/>
新的报表文件*reportType*。

## <a name="return-value"></a>返回值

在成功完成， **_CrtSetReportFile**返回以前的报表文件中指定的报表类型为定义*reportType*。 如果在传递一个无效值*reportType*，此函数将调用无效参数处理程序，如中所述[参数验证](../../c-runtime-library/parameter-validation.md)。 如果允许执行继续，则**errno**设置为**EINVAL**和该函数将返回 **_CRTDBG_HFILE_ERROR**。 有关详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

**_CrtSetReportFile**用于[_CrtSetReportMode](crtsetreportmode.md)函数定义的目标或生成的特定报表类型的目标 **_CrtDbgReport**。 当 **_CrtSetReportMode**已调用将分配 **_CRTDBG_MODE_FILE** reporting 模式对于特定报表类型， **_CrtSetReportFile**然后应调用到定义的特定文件或流要用作目标。 当[_DEBUG](../../c-runtime-library/debug.md)未定义，则调用 **_CrtSetReportFile**在预处理过程中删除。

以下列表显示的可用选项*reportFile*和产生的行为 **_CrtDbgReport**。 在 Crtdbg.h 中将这些选项定义为位标志。

- **文件句柄**

   将作为消息目标的文件的句柄。 不会尝试验证该句柄的有效性。 必须打开并关闭该文件的句柄。 例如：

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   将消息写入**stderr**，其中，可以重定向，如下所示：

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   将消息写入**stdout**，其中你可以重定向。

- **_CRTDBG_REPORT_FILE**

   返回当前报告模式。

可以单独控制每种报告类型所使用的报表文件。 例如，很可能指定*reportType*的 **_CRT_ERROR**报告给**stderr**，虽然*reportType*的 **_CRT_ASSERT**报告给用户定义的文件句柄或流。

## <a name="requirements"></a>要求

|例程|必需的标头|可选标头|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

通用 Windows 平台 (UWP) 应用中不支持控制台。 控制台中，与关联的标准流句柄**stdin**， **stdout**，和**stderr**，必须将 C 运行时函数才能使用它们在 UWP 应用重定向. 有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

**库：** 仅限 [CRT 库功能](../../c-runtime-library/crt-library-features.md)的调试版本。

## <a name="see-also"></a>请参阅

[调试例程](../../c-runtime-library/debug-routines.md)<br/>
