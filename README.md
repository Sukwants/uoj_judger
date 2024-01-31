# UOJ Judger

适用于 UOJ 社区版（也可能是特指 124OJ）的 Judger，你可以用超级管理员权限为题目上传自定义 Judger ~~（不会还有人没有 root 密码吧）~~。注意，如果你有服务器 root 权限也不能直接替换掉 OJ 的 Judger，但你只需要在本项目基础上稍作修改即可。

## Usage

你只需要用超级管理员权限，在数据包里加入本项目 `src` 文件夹中的文件，并在 `problem.conf` 中删除 `use_builtin_judger` 一行。

如果题目需要使用 Special Judge，请在 `Makefile` 中第 4 行加入 SPJ 文件名，如 `chk`。

## Features

### 子任务类型：almost

《你几乎通过了子任务内的所有测试点》。

在这个子任务类型模式下，你只需要通过了子任务内 80% 的数据点即视为通过了这个子任务。

使用方法是在 `problem.conf` 里添加形如 `subtask_type_1 almost` 的一行。

### 小数时间限制

你可以将 `time_limit` 设为小数，实际评测时将会四舍五入到小数点后 3 位。

## Fixes

### 子任务依赖的传递性问题

在修改版的 Judger 中，被 Skipped 的子任务也会被认为不通过，也就是 Skip 掉依赖被 Skipped 的子任务的子任务。
