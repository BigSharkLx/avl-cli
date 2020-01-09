English | [简体中文](./README.md)

<p align="center"><img width="100" src="https://vuejs.org/images/logo.png"></p>

<h2 align="center">avl-cli（一个简单的前端CLI工具）</h2>
<p align="center"><b>基于Node搭建生成个人前端脚手架（vue）</b></p>
# 目录

- [feature](#feature )
- [QuickStart](#QuickStart)
  - [Install](#Install)
  - [Usage](#Usage)
- [Contribution](#Contribution)
- [Maintainers](#Maintainers)
- [License](#license)

### feature

- Easy to use
- Support custom template addition and deletion

### QuickStart

### Install

```bash
$ npm i avl-cli -g               # install cli
$ omi init my-app     # init project, you can also exec 'omi init' in an empty folder
$ cd my-app           # please ignore this command if you executed 'omi init' in an empty folder
$ avl init [templateName] [yourProjectName]
```

Install description:

The default scaffolding template name is vue-admin
> avl init vue-admin [yourProjectName]

### New template usage

```bash
avl add
# Select template and template address (github address)
```

![avl-add](./img/readme_add.png)

- Note: The template address is the git repository name
![avl-add](./img/readme_gitAddress.png)

### Remove template usage

```bash
avl delete
# 选择模板
```

![avl-add](./img/readme_delete.png)


### See all template usage

```bash
avl list
```

### Initialize project scaffolding usage

```bash
avl init 或者 avl init [templateName] [yourProjectName]
```

![avl-add](./img/readme_init.png)


## Contribution
- BigSharkLx

## Maintainers

- [BigSharkLx](https://github.com/BigSharkLx)

## License

- [MIT](https://opensource.org/licenses/MIT)
