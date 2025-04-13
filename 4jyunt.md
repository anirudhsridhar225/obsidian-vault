
```ts
#!/usr/bin/env node

/**
 * MajDori CLI Tool
 * A command-line interface for creating boilerplate web projects with integrated services
 * 
 * @module MajDoriCLI
 * @author Dori
 */

import { confirm, input, select } from "@inquirer/prompts";
import chalk from "chalk";
import { execSync } from "child_process";
import fs from 'fs';
import path from "path";

/**
 * Interface representing the configuration options collected from user input
 * @interface ProjectAnswers
 */
interface ProjectAnswers {
    /** Name of the project to be created */
    projectName: string;
    /** Selected web framework (nextjs, svelte, or astro) */
    framework: string;
    /** Whether to use the pre-configured template */
    template: boolean;
    /** PostgreSQL database username */
    pgresUsername: string;
    /** PostgreSQL database password */
    pgresPassword: string;
    /** PostgreSQL database name */
    pgDbName: string;
    /** Grafana dashboard password */
    grafana: string;
    /** Email address for Traefik SSL certificates */
    traefikEmail: string;
    /** Cloudflare API token for DNS configuration */
    cloudflareToken: string;
}

/**
 * Main function that runs the CLI application
 * Handles user input collection, project creation, and environment setup
 * 
 * @async
 * @function main
 * @throws {Error} Will throw an error if project creation fails
 */
async function main() {
    try {
        // Display welcome message
        console.log(chalk.italic(chalk.blue("Welcome to MajDori, the only boilerplate template you'll ever need")));

        /**
         * Collect project name from user
         * @type {string}
         */
        const projectName = await input({
            message: "What is your project name?",
            default: "my-project",
        });

        /**
         * Collect framework choice from user
         * @type {string}
         */
        const framework = await select({
            message: "Which framework do you want to use?",
            choices: [
                {
                    name: "NextJS",
                    value: "nextjs",
                },
                {
                    name: "Svelte",
                    value: "svelte",
                },
                {
                    name: "Astro",
                    value: "astro",
                },
            ],
        });

        /**
         * Determine if user wants to use the pre-configured template
         * @type {boolean}
         */
        const template = await confirm({
            message: `
            Do you want to use a template?
            Our template contains a ${framework} project integrated to a logging service, a database,
            an ORM (prisma), husky (linting), prettier (formatter).
            `,
            default: true,
        });

        // Display database configuration prompt
        console.log(chalk.italic(chalk.blue("You will now be prompted to enter your database details")));
        console.log(chalk.italic(chalk.blue("This is to create the local .env file.")));
        console.log(chalk.italic(chalk.blue("We will not retain any data entered in this cli. All of this data will be used only to create the template for you.")));

        /**
         * Collect database configuration details
         */
        const pgDbName = await input({
            message: 'Enter your postgreSQL db name.',
            default: "my-database"
        });

        const pgresUsername = await input({
            message: 'Enter your postgreSQL db username.',
            default: 'my-user'
        });

        const pgresPassword = await input({
            message: 'Enter your postgreSQL db password.',
            default: 'lolxd69420'
        });

        const grafana = await input({
            message: 'Enter your grafana password.',
            default: 'lmaodeadlmaodead'
        });

        const traefikEmail = await input({
            message: 'Enter the email you want to use for traefik.',
            default: 'anbc@gmail.com'
        });

        const cloudflareToken = await input({
            message: 'Enter your cloudflare token (lmao lmao)',
            default: '123fegre35wfew'
        });

        /**
         * Consolidate all user inputs into a single configuration object
         * @type {ProjectAnswers}
         */
        const answers: ProjectAnswers = {
            projectName,
            framework,
            template,
            pgresUsername,
            pgresPassword,
            pgDbName,
            grafana,
            traefikEmail,
            cloudflareToken
        };

        /**
         * Generate the project directory path
         * @type {string}
         */
        const projectPath = path.join(process.cwd(), answers.projectName);

        // Clone template repository if template option is selected
        if (template) {
            const templatePath = `https://github.com/majdori/template-${answers.framework}.git`;
            console.log(chalk.blue(`Creating project from template: ${templatePath}`));
            execSync(`git clone ${templatePath} ${projectPath}`);
            execSync(`cd ${projectPath} && rm -rf .git && git init`);
        }

        /**
         * Generate environment variables for database configuration
         */
        const POSTGRES_USER = answers.pgresUsername;
        const POSTGRES_PASSWORD = answers.pgresPassword;
        const POSTGRES_DB = answers.pgDbName;

        /**
         * Create environment file content with all necessary configuration
         * @type {string}
         */
        const envBoilerplate = `
PROJECT_NAME=${answers.projectName}

#TRAEFIK
TRAEFIK_EMAIL=${answers.traefikEmail}
DATA_PATH=./traefik_data
CLOUDFLARE_DNS_API_TOKEN=${answers.cloudflareToken}

#POSTGRES
POSTGRES_USER=${answers.pgresUsername}
POSTGRES_PASSWORD=${answers.pgresPassword}
POSTGRES_DB=${answers.pgDbName}
DATABASE_URL="postgresql://${POSTGRES_USER}:${POSTGRES_PASSWORD}@postgres:5432/${POSTGRES_DB}?schema=public" 
POSTGRES_VOLUME=./postgres
NOCODB_VOLUME=./nocodb

#PINO
GRAFANA_PASSWORD=${answers.grafana}
        `;

        // Write environment file to project directory
        fs.writeFileSync(
            path.join(projectPath, '.env'),
            envBoilerplate
        );

        // Display success message with next steps
        console.log(chalk.green(`
Successfully created project: ${projectName}
To get started:
cd ${answers.projectName}
npm install
npm run dev        
`));
    } catch (error) {
        if (error instanceof Error) {
            console.error(chalk.red(`Error: ${error.message}`));
        } else {
            console.error(chalk.red("An unexpected error occurred"));
        }
        process.exit(1);
    }
}

/**
 * Entry point of the CLI application
 * Catches and handles any unhandled errors from the main function
 */
main().catch((error) => {
    console.error(chalk.red(`Fatal error: ${error}`));
    process.exit(1);
});
```


#jheyanth 
actually coding on this thing might actually be a sick experience, I am not even missing the keys
the option button to delete the word is in fact so much better than the control key because I dont have to reach over quite far just to delete a word, so it is pretty sick

the travel on the keys is just perfect, nothing too stretched out to throw me whack, and nothing too compressed like the lenovo default keyboard, both of which takes a long time to adapt to, but with this you can just start typing away immediately

the colour gamut on this screen seems insanely good too, idk how to fit something like this into something this thin at all, frankly feels like some alchemy

super portable, satisfying keystrokes, nice screen, i think i am in love tbh
how much even is this thing

if only it wasnt a walled garden with everything being paid software, I would really really consider this. Unfortunately the lack of flexibility has me considering second rate windows options like asus zenbook a14

the opps done apple pilled me at 10am in the morning chat
apple is opps 🤫