---
layout: default
title: Privacy Policy
permalink: /privacy/
---

Privacy Policy
Last updated: 2026-07-12

Who we are
Lurea is a Discord bot and Discord app operated by Didem Sahin.

Lurea helps Discord server owners understand community activity, run engagement features, and manage server tools such as XP, leaderboards, welcome cards, tickets, giveaways, reaction roles, invite tracking, rules verification, birthday cards, and setup flows.

Contact: didemsahin2468@gmail.com or Discord Support Server: https://discord.gg/E9txAGt49U

What data Lurea collects
Lurea collects and stores data needed to operate its features. This generally includes:

Discord identifiers: server (guild) ID, user ID, channel ID, role ID where needed for features, and message ID where needed for features or references
Activity metadata, such as:
message counts and hourly activity counters
reply presence (whether a message is a reply) and mention presence may be read transiently during message XP calculation; these flags are not stored in the database — only the resulting XP amount and message-count aggregates (for example, weekly_message_xp, points, message_count) are persisted
voice activity duration (not voice audio)
match and event participation counts
XP, points, levels, badges, and leaderboard statistics
Server configuration: setup state, selected channels, feature settings, and server type preferences
Minimal server metadata for operation and support, such as:
server name
approximate member count
bot join, last-seen, and leave timestamps
Admin-configured text and URLs provided by server owners or administrators, including embed titles, descriptions, footers, button labels, custom background image URLs, panel image/thumbnail URLs, ticket opening messages, ticket form question labels and placeholders, cross-server event text fields, and giveaway prize/description text. These are stored as configuration text or URL strings in Lurea’s database as entered by the server administrator.
Discord message IDs used as references where a feature needs to locate a posted message (for example, clip submissions, conversation-starter replies, rules verification posts, ticket panel posts, cross-server feed posts, reaction role panel posts, or giveaway messages). Lurea stores the ID, not the full message body, for these reference paths.
Feature-specific data, including:
ticket metadata (opener, status, channel references; form answers are posted to the Discord ticket channel only and are not stored in the Lurea database)
ticket ratings (rating value, ticket/server/user references, and timestamps where stored)
birthday dates submitted by users (day and month; year optional)
welcome card settings (card text, embed text, accent/background settings, optional custom background URL; no per-user welcome profile stored)
birthday card settings (optional custom background URL and related card configuration)
rules verification settings (embed text, image/thumbnail URLs, verification emoji, channel and message references)
ticket panel configuration (embed text, button label, image/thumbnail URLs) and ticket form question definitions (labels and placeholders only)
Invite tracking: invite codes, inviter user IDs, invited user IDs, guild/server IDs, channel IDs, join timestamps, and attribution data used for invite statistics and leaderboards
Reaction role panels: panel configuration, emoji identifiers, role IDs, channel IDs, message IDs, and creator/admin user IDs where needed
cross-server event records (event title, description, hero text, prize text, rules text, participation instructions, and related host metadata) plus interest registrations: when a user clicks interested, Lurea stores event_id, user_id, feed_guild_id, and a timestamp (created_at). This is user-initiated. Rows are deleted when the feed guild removes the bot, or when the host event is deleted via parent-record cascade
giveaway records (prize and description text, participant entries, winner records; optional source_message_id when staff approve a feedback bonus)
Top.gg vote records linked to a Discord user ID, including vote timestamps, expiry time, vote weight, and optional notification reference IDs
Vote Pass: uses Top.gg vote records and Discord user IDs of voters; guild/server IDs where a staff vote may count; vote timestamps and expiry time; and staff eligibility checks based on owner, administrator, or Manage Server status. Vote Pass is optional, Top.gg vote-based, and not a paid subscription. Core features work without Vote Pass.
Auto Rescue: opportunity intervention records, temporary voice session metadata, and user/guild/channel/message IDs where needed, plus timestamps and operational metadata only
privacy preference flags (for example, tracking opt-out per server)
server health weekly report administrator IDs (weekly_dm_user_ids in server_health_settings): the server owner may configure up to 3 administrator user IDs via /health_report_enable; these IDs are stored as a JSONB list. Weekly health reports are sent via configured channel posts and a server-owner DM; the stored weekly_dm_user_ids list is not used as a DM recipient list. These IDs are deleted on guild removal.
Feedback submitted through /feedback — sent as a Discord embed to an internal operator feedback channel; feedback message content is not stored in Lurea’s database. Lurea may store a guild-level flag that feedback was submitted
Clip and media event submissions (/clip, /video, and related event types): for new submissions, Lurea does not store Discord CDN URLs or original upload filenames in its database. Lurea stores the submitter’s user ID, the Discord message ID of the bot-posted submission message, a placeholder media type value (clip or video), and an aggregate reaction count per submission (individual reacting user IDs are not stored). The media file is posted to the event Discord channel and remains on Discord’s infrastructure; it is not stored in Lurea’s database. Conversation-starter submissions (a separate event path) store a user reply message ID and a placeholder filename (message_reference), not message content; if the same user submits again in the same event, the prior row is replaced. Legacy rows from before a privacy refactor may still contain attachment URLs or original filenames; no automated cleanup of these legacy values has been completed — they remain until guild removal, deletion of the parent event record, or a manual deletion request
Lurea may temporarily read message content in memory to derive metadata (such as whether a message is a reply or contains mentions). Raw Discord message text is not stored in Lurea’s database or application logs for analytics or long-term records. Lurea does not write per-message character length to the database — only message counts and XP aggregates are stored. Older database rows from earlier versions of Lurea may still contain historical metadata fields until those rows are removed through guild removal, parent-record deletion, or a manual deletion request.

What data Lurea does not collect
Lurea is designed to limit stored personal data. Specifically:

Lurea does not store raw Discord message content in its database or logs for analytics or long-term records (see Clip and media event submissions above for feature-specific exceptions and legacy rows)
Lurea does not permanently store full message bodies or feedback message content for new clip/video submissions, /feedback, giveaway feedback text, ticket form answers, conversation-starter replies, or general Auto Rescue reply text in its database
Lurea does not record or store voice audio
Lurea does not store full member lists in its database (member information may be read from Discord when needed for a feature, then used in memory)
Lurea does not permanently store fetched custom background image files, Discord avatars, server icons, or banners as Lurea-owned media assets on disk or in the database
Lurea does not persist generated welcome, birthday, or weekly leaderboard card image files in its database after posting (cards are rendered in memory and sent to Discord as attachments)
Lurea does not sell user or server data to third parties for advertising or marketing
Lurea does not use data for employment, housing, insurance, credit, or similar eligibility decisions
Lurea is not designed to collect sensitive personal data categories (such as health, religion, or government ID numbers)
Vote Pass does not involve payment or a paid subscription
How we use data
Lurea uses data to:

Provide XP, levels, badges, and leaderboards
Generate community analytics and health insights for server owners
Run activation and engagement features
Operate tickets, welcome cards, reaction roles, invite tracking, giveaways, rules verification, birthday cards, and server setup tools
Process Top.gg vote bonuses and optional Vote Pass unlocks where enabled
Send operational messages (for example, welcome posts or ticket notifications)
Improve reliability, debugging, and abuse prevention
Respond to feedback and support requests
Operate internal bot administration, support, and reliability monitoring
Vote Pass
Vote Pass is an optional feature based on active Top.gg votes from eligible server staff (such as the server owner, administrators, or members with Manage Server permission).

Vote Pass may unlock optional customization or capacity features — for example, additional reaction role panel capacity or continued server-icon welcome background access after a trial.

Vote Pass is not a paid subscription. Core features remain usable without Vote Pass. Vote Pass availability may depend on Top.gg, Discord, and Lurea’s ability to verify active votes.

Internal server registry
Lurea maintains a limited guild registry (guild_registry) with minimal server metadata: server ID, server name, approximate member count, and bot join, last-seen, and leave timestamps.

This registry is used to operate the bot, provide support, debug issues, improve reliability, and manage internal administration. It does not store member lists or message content.

When Lurea is removed from a server, most operational data for that server is deleted automatically, but the registry record is typically soft-deleted (marked inactive with a leave timestamp) rather than fully erased. Server owners may request removal of registry data by contacting us. See Data Deletion for details.

Who can see the data
Server owners and administrators

May see community analytics dashboards, top-member views, retention or at-risk activity insights, activity trends, invite leaderboards, and similar admin-facing tools
Access is restricted to admin or owner roles and configured permission rules in the bot
Server members

May see the weekly leaderboard if the server owner configured a public leaderboard channel
May see their own XP and stats via commands such as /stats
Lurea operator

May see feedback submitted via /feedback in the internal feedback channel
Has access to the database for maintenance, debugging, and support
Does not routinely review individual user activity
Third parties

Lurea does not sell or share user data with third parties for advertising or marketing
Infrastructure providers (hosting, database, Discord, Top.gg) process data only as needed to operate the service (see Third-party services below)
On Lurea’s own support or demo server, some features may be visible more broadly for testing, support, and feedback purposes.

Activity insights and profiling
Lurea provides activity-based insights such as top members, activity trends, and retention patterns (for example, labels suggesting fading or at-risk activity).

These insights:

Are based on observed activity metadata (such as message counts, voice duration, and participation), not message content
Are intended to help server owners understand community health
Are visible to server owners and administrators by default, except where owners enable public leaderboards
Lurea does not make automated decisions with legal or significant personal effects on individual users.

Admin-configured content, URLs, and transient media
Server owners and administrators may configure text, embeds, and URLs through Lurea features. Lurea stores this configuration as text or URL strings in its database when you save settings.

Stored URL strings may include, for example, welcome or birthday custom background URLs, rules verification embed image/thumbnail URLs, and ticket panel image/thumbnail URLs. Lurea does not operate these third-party hosts.

Transient fetching. When rendering welcome cards, birthday cards, or weekly leaderboard cards, Lurea may temporarily fetch:

External background URLs you configured (into memory only at render time)
Discord user avatars, server icons, and (where used in embeds) server banners from Discord/CDN sources
These assets are used to generate images or embeds. Lurea does not store them as permanent Lurea-owned media files. Generated card images may be posted to Discord as message attachments; Lurea does not persist those generated image files in its database.

Message references. Where features post or reference Discord messages, Lurea may store message_id values (and related channel/guild IDs) to operate the feature. This includes, for example, clip/video submission messages, conversation-starter reply references, rules verification posts, ticket panel posts, reaction role panel posts, cross-server feed posts, birthday announcement posts (birthday_posts), and giveaway messages. Stored IDs are metadata references; they are not a copy of the underlying message body.

For content responsibility, reporting, and enforcement boundaries, see Terms of Service.

Data by feature
Feature	Typical data
Messages & XP	User ID, channel ID, message counts, XP amounts, hourly activity rollups
Voice activity	User ID, voice duration in seconds, channel ID for events
Leaderboards & stats	User ID, points, wins/losses, voice and message XP
Server setup	Guild ID, configured channels, server type, setup completion state
Community analytics	Aggregated activity trends, hourly rollups, admin-facing insights
Welcome cards	Guild settings (card text, embed text, accent/background mode, optional custom_background_url); user avatar and server icon fetched temporarily from Discord for rendering
Birthday cards	User-provided day/month (optional year) per server; guild birthday settings including optional custom_background_url; birthday_posts rows with stored message_id references for sent birthday posts; user avatar and server icon fetched temporarily for rendering
Weekly XP leaderboard cards	Leaderboard stats (user IDs, XP); optional card style setting; user avatars and server icon fetched temporarily for rendering
Rules verification	Embed title, description, footer, color, image/thumbnail URLs, verification emoji, channel ID, rules message_id
Tickets — panel	Panel embed title/description, button label/emoji, footer, embed color, image_url, thumbnail_url, panel message_id
Tickets — types & forms	Type name, description, opening message text, form question labels/placeholders/styles; opener/staff user IDs, ticket status, channel ID
Tickets — form answers	Not stored in Lurea database — answers appear in the Discord ticket channel only
Tickets — ratings	Rating value, ticket reference, user ID, guild ID, timestamps where stored
Invite tracking	Invite codes, inviter user IDs, invited user IDs, guild ID, channel IDs, join timestamps, attribution method
Reaction role panels	Panel title/description/mode, guild ID, channel ID, message ID, emoji identifiers, role IDs, creator user ID
Clip / video events	Submitter user ID, channel ID, submission message_id, placeholder media type, reaction count; media file remains on Discord
Conversation-starter (Auto Rescue)	User reply message_id and placeholder message_reference label; reply text remains on Discord
Auto Rescue — interventions	Guild ID, intervention type, optional channel/message IDs, JSONB metadata, timestamps
Auto Rescue — temporary voice sessions	Guild ID, channel/message IDs, voice channel references, session status, timestamps, operational metadata
Giveaways	Prize and description text, participant user IDs, entry counts, winner records; optional source_message_id for staff-approved feedback bonus; giveaway message_id where posted
Giveaway feedback text	Feedback message content not stored in Lurea database — posted to configured Discord channel
Feedback (/feedback)	Feedback message content not stored in Lurea database — sent as Discord embed to operator channel; guild-level feedback_submitted flag may be stored
Cross-server events	Event title, description, hero text, prize text, rules text, participation instructions, host metadata, feed message_id references; interest rows: event_id, user_id, feed_guild_id, timestamp
Top.gg votes	Discord user ID, vote time, expiry time, vote weight, optional notify guild/channel/message IDs, webhook scope (stored globally, not per guild)
Vote Pass	Derived from Top.gg vote records and staff eligibility checks; optional unlock state for supported features; not a paid subscription
Privacy controls	Per-user, per-server tracking opt-out preference
Server health reports	Up to 3 administrator user IDs in weekly_dm_user_ids (server-owner configured); weekly channel report and server-owner DM
Ticket transcripts	Ticket message content is not stored in Lurea’s database. Ticket channel content remains on Discord.
Guild removal and data retention
When Lurea is removed from a server, most guild configuration and operational data supported by automatic cleanup is deleted where automatic guild-removal cleanup applies. See Data Deletion for the non-exhaustive list of what is deleted automatically.

Some data may remain in Lurea’s database after bot removal if it is not covered by automatic cleanup, including:

guild_invite_cache
invite_attributions
role_panels / role_panel_options
auto_rescue_temporary_voice_sessions
birthday records, ticket ratings, Top.gg vote records, guild registry metadata, and auto-rescue intervention records (see Data Deletion)
Server administrators may request deletion of remaining data through didemsahin2468@gmail.com or the Discord Support Server: https://discord.gg/E9txAGt49U

Deletion boundaries (Lurea vs Discord and third parties)
Lurea can delete Lurea-controlled configuration, metadata, references, and related database records as described in Data Deletion (for example, on bot removal or approved manual requests).

Lurea cannot delete or modify content hosted on Discord (messages, attachments, channels, embeds, ticket channel posts, feedback embeds, welcome posts, rules posts, giveaway posts, event posts, clip/video files) or on third-party URL hosts you link (for example, a custom background image host). Removing Lurea or deleting Lurea-held data does not automatically remove Discord-hosted or third-party-hosted content. Server owners and administrators remain responsible for Discord-side cleanup where needed.

Lurea does not guarantee deletion from Discord CDN, external image hosts, Top.gg, database infrastructure providers, or other third-party systems beyond Lurea-controlled application data.

Third-party services
Lurea relies on third-party services to operate:

Service	Role	Location
Discord	Platform, API, and content delivery (avatars, channels, messages)	Processing locations depend on Discord’s infrastructure and policies
Top.gg	Vote webhooks and bot statistics (server count) where enabled	Processing locations depend on Top.gg’s infrastructure and policies
Supabase PostgreSQL	Primary database hosting	EU region where configured
Contabo VPS	Bot application hosting	Germany
Data may be processed in these locations as necessary to operate Lurea. Their own privacy policies and terms apply to their services.

Lurea uses infrastructure providers located in Germany or the European Union where available. Database availability, redundancy, and backup behavior may depend on the infrastructure provider and plan in use. Lurea does not use backups for advertising, profiling, or unrelated purposes.

Data retention
Retention practices may change as Lurea develops. At a high level:

Server settings are kept while Lurea is installed in a server
Hourly activity rollups (server_activity_hourly) are deleted automatically after approximately 30 days
Other tables (for example, player_stats, ticket records, revive_clip_submissions) have no automated time-to-live deletion while the bot is installed; they are retained unless deleted manually or through guild-removal cleanup where applicable. Birthday records (birthday_settings, user_birthdays, birthday_posts) are not removed by standard guild-removal cleanup (see Data Deletion). Invite tracking, reaction role panels, and auto-rescue temporary voice sessions are also not removed by standard guild-removal cleanup. Clip/media submission rows are not deleted when an event ends
When Lurea is removed from a server, most operational data for that server is deleted automatically where supported (see Data Deletion and Guild removal and data retention above)
A limited guild registry record may be soft-deleted but retained (server ID, name, member count, leave timestamp)
Top.gg vote records are stored per user globally and are not automatically deleted when a single server removes the bot
Feedback sent via /feedback remains in the operator’s internal Discord feedback channel until manually removed there — feedback message content is not stored in the Lurea database; a guild-level flag that feedback was submitted may be stored
Infrastructure and backups: see Third-party services above
Server logs: used for operational security, troubleshooting, and abuse prevention; log retention depends on host configuration and may vary (see Data minimization and security below)
Data deletion and access requests
You can request access to, correction of, or deletion of data related to you or your server.

Server owners: see Data Deletion for guild-level deletion and what remains after bot removal
Users: use /privacy optout in a server to stop new message XP and new voice tracking and clear in-memory buffers (see limitations below). Lurea does not currently offer a fully automated self-service command that deletes all historical database rows for a user — broader deletion requires contacting us
Manual requests: contact us using the details below
What /privacy optout does: stops new message XP accumulation and new voice tracking for you in that server and clears buffered in-memory data immediately. For voice, new writes such as voice_seconds, voice_xp, weekly_voice_seconds, revive voice participant records, and server_activity_hourly voice columns are blocked for opted-out users. Secondary XP paths (such as XP poll votes and daily or speed-challenge XP triggered by commands) are also blocked for opted-out users.

Public display filtering: opted-out users are excluded from public leaderboard and Server Health user-list outputs in that server. This includes weekly and match leaderboards (including weekly leaderboard cards), rank lookups (returning Unranked rather than a public rank), and Server Health analytics user lists (including top users, participation mix, retention, and at-risk views). Opted-out users do not appear in these public outputs.

What /privacy optout does not do: delete existing rows in player_stats, server_activity_hourly, or other historical database records. Historical activity data is retained by design and may still appear when you view your own stats (for example via /stats), unless separately deleted through a manual request. Opt-out does not affect voluntary or social features that are separate from message/voice activity tracking unless specifically stated otherwise — for example, giveaway entries, birthday announcements, cross-server event interest registrations, clip or video submission metadata, and ticket activity. Full deletion of historical records requires a manual support request.

Note: The in-bot /privacy status command shows voice tracking as stopped for opted-out users. Public leaderboard and Server Health user-list filtering described above applies to opted-out users in that server. Self-view of your own historical stats and the voluntary features listed above are not covered by this opt-out.

Contact for privacy requests: didemsahin2468@gmail.com or Discord Support Server: https://discord.gg/E9txAGt49U

We handle deletion requests manually. The target processing time is within 30 days. Complex cases may require identity verification. Some minimal technical logs may persist temporarily after a deletion request depending on host log retention (see Data retention above). Some data may also be retained where needed for security, abuse prevention, or legal obligations.

Deletion of Lurea-held records (including configuration text, stored URLs, and message_id references) does not by itself delete the underlying Discord messages, attachments, or third-party-hosted files those references point to. See Deletion boundaries (Lurea vs Discord and third parties) above and Data Deletion.

Data minimization and security
Lurea is designed to collect only data needed for its features and to avoid storing unnecessary personal data.

Raw message content is not stored in the database or logs
Database access is limited to the operator
Credentials and tokens are not intentionally published
Application logs are used for operational security, troubleshooting, and abuse prevention. Log retention depends on host configuration and may vary. Logs are accessible only to the operator. Lurea uses logging helpers designed to reduce unnecessary personal data in logs, such as masking identifiers and redacting message-like fields where supported.

No system can be guaranteed completely secure. If you notice a security concern, please contact us using the contact details above.

Data protection principles
Lurea is designed around data minimization, transparency, and privacy-conscious defaults. We aim to process only the data needed to operate the requested bot features and provide opt-out and deletion request paths where technically available.

If you have questions about your data, contact us using the details above.

Children / age note
Lurea is not directed at children under 13. Discord’s own terms require users to be at least 13 years old. We do not knowingly collect data from users under 13. Server owners are responsible for appropriate use within their communities.

Changes to this policy
This policy may be updated as Lurea changes. The “Last updated” date at the top reflects the most recent revision. Continued use of Lurea after changes means you accept the updated policy.

Contact
For privacy questions or data requests:

didemsahin2468@gmail.com or Discord Support Server: https://discord.gg/E9txAGt49U

Related documents:

Privacy Policy
Terms of Service
Data Deletion
Impressum
