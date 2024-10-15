在 macOS 上，您可以通过修改您的 shell 配置文件来将 `$GOPATH/bin` 添加到环境变量中。常见的 shell 配置文件包括 `~/.bash_profile`、`~/.bashrc`、`~/.zshrc` 等，这取决于您使用的是 Bash 还是 Zsh shell 或其他类型的 shell。

以下是向 `PATH` 环境变量添加 `$GOPATH/bin` 的步骤：

### 如果您使用的是 Bash：

1. 打开终端。
2. 输入以下命令编辑 `.bash_profile` 或 `.bashrc` 文件（如果您不确定哪个文件存在，可以使用 `ls -a ~` 命令检查）：

```sh
open -e ~/.bash_profile  # 或者 open -e ~/.bashrc
```

3. 在打开的文本编辑器中，添加以下行到文件末尾：

```sh
export PATH=$PATH:$(go env GOPATH)/bin
```

4. 保存并关闭文件。
5. 要使更改立即生效，执行以下命令：

```sh
source ~/.bash_profile  # 或者 source ~/.bashrc
```

### 如果您使用的是 Zsh：

1. 打开终端。
2. 输入以下命令编辑 `.zshrc` 文件：

```sh
open -e ~/.zshrc
```

3. 在打开的文本编辑器中，添加以下行到文件末尾：

```sh
export PATH=$PATH:$(go env GOPATH)/bin
```

4. 保存并关闭文件。
5. 要使更改立即生效，执行以下命令：

```sh
source ~/.zshrc
```

请注意，如果您的 Go 版本较新，且没有特别设置 `GOPATH`，Go 会默认使用 `$HOME/go` 作为 `GOPATH` 的值。因此，上述命令行中的 `$(go env GOPATH)` 就能确保正确地引用 `GOPATH` 的当前值。

进行这些更改之后，每次打开新的终端窗口时，`$GOPATH/bin` 都会自动包含在 `PATH` 环境变量中，使得您可以全局运行那里的可执行文件。
