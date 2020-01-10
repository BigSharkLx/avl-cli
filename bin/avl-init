#!/usr/bin/env node
// 交互式命令行
const inquirer = require("inquirer");
const program = require("commander");
const chalk = require("chalk");
const ora = require("ora");
const download = require("download-git-repo");
const tplObj = require(`${__dirname}/../template`);

program.parse(process.argv);

// 好比 vue init webpack project-name 的命令一样，第一个参数是 webpack，第二个参数是 project-name
let templateName = "";
let projectName = "";

let question = [
  {
    name: "projectName",
    type: "input",
    message: "请输入项目名称",
    validate(val) {
      if (val === "") return "The projectName is required!";
      return true;
    }
  }
];

const promptList = [
  {
    type: "list",
    message: "请选择一个模板:",
    name: "templateName",
    choices: Object.keys(tplObj),
    validate(val) {
      if (val === "") {
        return "请先创建模板";
      }
    }
  }
];

// 当没有输入参数的时候给个提示
if (program.args.length < 1) {
  inquirer
    .prompt(promptList)
    .then(answers => {
      templateName = answers.templateName;
    })
    .then(() => {
      inquirer.prompt(question).then(answers => {
        projectName = answers.projectName;
        startProject();
      });
    });
} else {
  templateName = program.args[0];
  projectName = program.args[1];
  // 小小校验一下参数
  if (!tplObj[templateName]) {
    console.log(chalk.red("\n Template does not exit! \n "));
    return;
  }
  if (!projectName) {
    console.log(chalk.red("\n The projectName is required! \n "));
    return;
  }
  startProject();
}

// 开始下载脚手架的流程
function startProject() {
  url = tplObj[templateName];

  console.log(chalk.white("\n Start generating... \n"));
  // 出现加载图标
  const spinner = ora("Downloading...");
  spinner.start();
  // 执行下载方法并传入参数
  download(url, projectName, err => {
    if (err) {
      spinner.fail();
      console.log(chalk.red(`Generation failed. ${err}`));
      return;
    }
    // 结束加载图标
    spinner.succeed();
    console.log(chalk.green("\n Generation completed!"));
    console.log("\n To get started");
    console.log(`\n    cd ${projectName} \n`);
    process.exit();
  });
}
