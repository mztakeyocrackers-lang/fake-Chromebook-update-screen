# @aurxora

I am @aurxora, a developer focused on building Discord-based operations systems for communities, roleplay groups, staff teams, and development groups that need more than basic bot commands.

My main project is Nexus, a Discord operations platform built around moderation support, ticketing, verification, applications, staff tools, protected dashboards, transcripts, automation, and secure role-based access. Nexus started around OCRP operations, but the long-term direction is to make it useful for more servers and groups without mixing up routing, permissions, or private server-specific systems.

I build systems for groups that need structure. That can mean a Discord server that needs better tickets, a roleplay community that needs staff workflows, a development group that wants cleaner member support, or a team that needs private dashboards and audit trails instead of scattered channels and manual logs.

## What I Build

I build Discord bots that use modern Discord features such as slash commands, buttons, select menus, modals, embeds, Components V2, role checks, and private ticket channels or threads. The goal is not just to make commands exist, but to make them feel organized and reliable when real users are using them.

I also build web dashboards that connect to Discord through OAuth. These dashboards can protect staff-only pages, show live records, display transcripts, manage documents, handle support tickets, and separate public pages from private tools. I care a lot about making dashboards feel like real products instead of rushed admin panels.

A lot of my work sits between Discord and the web. Nexus uses Discord for the actual community experience, while the dashboard gives staff a cleaner place to review records, tickets, documents, logs, and account-based access. This kind of setup is useful for groups that want their Discord server to stay clean while still having deeper tools behind it.

## Nexus

Nexus is the system I have spent the most time building and improving. It combines a Discord bot, a protected web dashboard, Supabase-backed data, OAuth login, ticket transcripts, application handling, department systems, and staff controls into one connected platform.

The bot side handles day-to-day Discord workflows. This includes announcements, embeds, polls, meetings, statements, reaction roles, alarms, ticket panels, staff commands, application actions, verification, moderation tools, and server-specific command routing.

The dashboard side gives staff a protected place to review information without exposing private data publicly. It includes pages for tickets, transcripts, documents, moderation tracking, login tracking, staff resources, department tools, audit logs, legal notices, and support flows.

The important part is that Nexus is not designed as one giant pile of commands. The goal is to keep each server's setup separate, make universal features reusable, and keep OCRP-specific systems locked to OCRP. That means a group can use general Nexus tools without inheriting private OCRP systems they should not have.

## Ticket Systems

A major part of Nexus is ticket support. I have worked on making tickets more flexible so they can work across different servers instead of only working for one community.

The newer ticket setup flow lets an administrator build a ticket panel from inside Discord. A panel can have up to five ticket types, and each ticket type can have its own staff role. That matters because different requests should not all route to the same staff team. A general support ticket, setup request, bug report, or privacy request may need different people watching it.

The panel setup also supports custom text, custom panel presentation, ticket type descriptions, emojis, category selection, transcript or log channel selection, and per-server role selection. Roles are selected from the server where the command is being used, which helps prevent one server from accidentally depending on another server's roles.

I have also worked on making the ticket flow look cleaner. Instead of forcing users through too many manual command options, the setup process uses a panel-style editor with a mix of buttons and dropdowns. The public ticket panel can open a ticket picker, then the user chooses the type that fits their request.

For OCRP, ticket presets still exist, but they are locked to OCRP only and require the OCRP leadership role. That prevents OCRP-specific routing from being exposed as a feature in unrelated servers.

## Nexus Support Portal

I rebuilt the old support and appeals system into a Nexus Tickets portal. The goal was to keep the parts that worked, such as OAuth, Supabase records, message ordering, evidence storage, staff notes, status changes, and audit history, while replacing the old interface with a cleaner ticket experience.

The support portal uses Discord login so users can open and return to their own tickets. Staff can review a queue, open a ticket thread, assign or claim a ticket, reply publicly, request more information, add internal notes, change status, and close the ticket.

The UI is designed to feel closer to Discord while still being a web product. Ticket messages are ordered chronologically, staff and requester messages are visually separated, and the composer stays attached to the workflow. This makes it easier for staff to follow the conversation without losing context.

For the first version, staff access is owner-only so the system can be tested and controlled before opening it up to more roles. That is intentional: I would rather launch a sensitive support system with narrow access first than accidentally expose private support data.

## Transcripts And Evidence

Nexus ticket transcripts are designed to preserve what happened in a ticket after it closes. I have worked on making transcript pages look more like Discord instead of stretched-out generic embeds.

The transcript renderer shows avatars, names, timestamps, message content, embeds, attachments, deleted-message markers, bot labels, and ticket summary details. The layout is meant to make a closed ticket readable later, especially when staff need to review why something happened.

I also worked on image handling for transcripts. Discord CDN links can expire or fail later, so Nexus can archive ticket image media into storage and show the archived version in the transcript. That makes evidence more dependable and prevents old transcripts from becoming useless because an image link stopped loading.

## Verification And Applications

Nexus includes Roblox and Discord verification workflows. These are useful for roleplay groups because server access often depends on whether a user is linked, verified, accepted, or part of a certain department.

Verification work includes protected web flows, Discord role assignment, verification result screens, accepted applicant handling, role swaps, and checks that prevent users from bypassing normal access rules.

Application systems are also part of the platform. Nexus can handle DM applications, applicant ticket panels, review actions, accept and deny results, cooldown handling, role changes, and logs. For OCRP, application routing is intentionally locked to the correct OCRP review areas so application actions do not go to the wrong place.

## Department Systems

A lot of Nexus development has focused on department-style groups. These are separate teams inside a larger community, such as CPD, ISP, ATF, or other linked departments.

Department tools can include shift tracking, shift panels, rosters, personnel records, arrests, promotions, demotions, infractions, blacklists, quota checks, leadership tools, private document libraries, and action logs.

The point of these systems is to let each department operate with its own structure while still being connected to the larger Nexus platform. Department commands and dashboard access can be scoped so users only see what they are supposed to manage.

I have also worked on command syncing for linked department servers. Instead of blindly pushing every command everywhere, Nexus can decide which commands belong in which guild. That helps make the bot more universal while still respecting server-specific boundaries.

## Reaction Roles And Server Setup

Nexus has custom reaction role panels that can be configured per server. These can include custom messages, selected roles, multiple role options, and emojis. The system is built so role options come from the server where the setup is being run.

This matters because reaction roles are one of those features that seem simple until they are used across multiple servers. If a bot is not careful, it can try to reference a role from the wrong server, expose old presets, or confuse staff trying to build a clean onboarding panel.

Nexus also includes setup-style commands for tickets, embeds, announcements, and other reusable systems. These commands are meant to require Administrator permission by default so random users cannot change server infrastructure.

## Security And Access Control

Security is one of the biggest parts of how I build Nexus. I do not treat permissions as something to add after the feature is finished. I try to design the feature around who should be allowed to use it, where it should work, and what data it should be able to touch.

Discord OAuth is used for protected web access. This means a user signs in with their Discord account before accessing private dashboard routes, support tickets, transcripts, staff documents, or department tools. OAuth gives Nexus a way to connect a browser session back to a real Discord user instead of relying on public URLs alone.

Role-based access checks are used so permissions come from actual Discord roles. For example, staff pages can check whether a user has a leadership, staff, manager, or department role before showing private tools. This is important because staff access changes over time, and the system needs to respect the current state of the Discord server.

Server-specific command scoping is another security step. OCRP-only features such as OCRP ticket presets, verification, applications, and internal staff tools are kept locked to OCRP. Universal features can be reused in other servers, but private OCRP systems should not appear as general Nexus features.

For setup commands, Nexus uses Administrator permission by default. Commands like ticket setup and reaction role setup can affect channels, roles, routing, and public panels, so they should not be available to normal members.

For ticket routing, I have worked to avoid fallback behavior that sends logs or transcripts to the wrong place. A ticket system should know which staff role, category, and transcript channel it belongs to. If something is missing, it should fail clearly instead of guessing and creating a privacy problem.

Sensitive keys and tokens are handled through environment variables instead of being committed into the codebase. Bot tokens, Supabase service-role keys, runtime state, transcripts, logs, and private generated data should stay out of Git. This keeps development safer and makes deployment cleaner.

The dashboard keeps privileged database operations on the server/API side instead of exposing service-role access to browser code. Public pages can exist, but private operations need to run behind protected server routes.

Audit logging is used for important actions. When staff change settings, use protected tools, update records, close tickets, or trigger system actions, Nexus can preserve those events so there is a record of what happened. This helps with accountability and makes it easier to debug problems later.

Cloudflare is used in front of public web routes. That adds another protection layer for the public-facing dashboard and support pages.

## Development Style

I build with the idea that real staff will use the system while busy, tired, or under pressure. That changes how I design things.

I try to make workflows clear instead of overloading people with raw IDs, confusing dropdowns, or too many buttons. When a feature needs a lot of configuration, I prefer guided panels and smaller steps. When a feature is dangerous, I prefer stricter permissions and clearer failure messages.

I also care about polish. A tool can technically work and still feel bad. Nexus has gone through many UI passes because I want the public pages, verification screens, transcripts, support portal, and dashboard tools to feel serious and consistent.

When I build something, I usually think through the full path: the command, the modal or menu, the backend record, the permission check, the Discord response, the logs, the dashboard view, the deployment, and the failure cases.

## Why Groups May Be Interested

Groups may be interested in working with me because I build systems that solve actual community operation problems.

If a group needs better ticket handling, I can build a setup that routes tickets to the right staff, stores transcripts, keeps evidence visible, and avoids mixing one server's configuration with another's.

If a group needs staff management tools, I can build systems for shifts, rosters, records, warnings, infractions, applications, blacklists, logs, and private dashboards.

If a group needs a cleaner public presence, I can build branded pages for support, verification, legal notices, data collection information, and community tools.

If a group needs stronger safety around their tools, I can build around OAuth, role checks, owner-only guards, admin-only setup, audit trails, and protected server routes.

My focus is not just making a bot respond to commands. My focus is making a full system that a group can rely on as it grows.

## Tools And Technologies

I mainly work with JavaScript, Node.js, Discord.js, React, Vite, Supabase, REST APIs, OAuth flows, Vercel, Cloudflare, Linux VPS deployment, PM2, Git, and GitHub.

Inside Discord, I work with slash commands, buttons, dropdown menus, role select menus, channel select menus, modals, embeds, Components V2, private threads, ticket channels, permission overwrites, role checks, and interaction routing.

On the web side, I work with protected routes, session handling, dashboard UI, staff portals, support portals, transcript renderers, document viewers, API wrappers, storage-backed uploads, and data-driven pages.

## Current Focus

My current focus is making Nexus more universal while keeping server-specific systems safe.

That means improving the parts that any group could use, such as tickets, reaction roles, support pages, announcements, embeds, reminders, and help commands, while keeping OCRP-only features locked to OCRP.

The goal is a Discord operations platform that feels polished, secure, and useful for serious communities and development groups.
