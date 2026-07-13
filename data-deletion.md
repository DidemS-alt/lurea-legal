---
layout: default
title: Data Deletion
permalink: /data-deletion/
---

# Data Deletion
Last updated: 2026-07-12

This page explains how server owners and users can request deletion of data related to Lurea, what happens automatically when the bot is removed from a server, and the limits of in-bot privacy controls.

Contact for deletion requests: didemsahin2468@gmail.com or Discord Support Server: https://discord.gg/E9txAGt49U

There is no fully automated self-service command that deletes all of a user’s historical database records. Manual deletion requests are handled via the contact method above.

## How server owners can request guild/server data deletion
If Lurea is still installed in your server, you can remove the bot from your Discord server. This triggers automatic deletion of most operational data (see below).

If you need additional deletion — for example, guild registry records, birthday data, ticket ratings, invite tracking data, reaction role panel data, or data after the bot was already removed — contact us at didemsahin2468@gmail.com or via the Discord Support Server: https://discord.gg/E9txAGt49U with:

Your server (guild) ID
Your server name
Your Discord username and confirmation that you are the server owner or an authorized administrator
A clear description of what you want deleted
We will review and process requests manually without undue delay. Under GDPR Article 12(3), we normally respond within one month of receiving your request. For complex or multiple requests, this period may be extended by up to two additional months where legally permitted; if an extension is necessary, we will inform you within the initial one-month period and explain the reasons. We may request identity or scope clarification where reasonably needed.

## How users can request deletion of user-related data
### In-server opt-out (partial — stops new tracking only)
Use /privacy optout in a server where Lurea is installed. This will:

Stop new message XP accumulation and new voice tracking writes for you in that server (including voice_seconds, voice_xp, weekly_voice_seconds, revive voice participant writes, and server_activity_hourly voice columns)
Block secondary XP write paths for opted-out users (such as XP poll votes and daily or speed-challenge XP triggered by commands)
Clear buffered in-memory tracking data for you immediately (including privacy-filtered revive message buffer flushes)
### What /privacy optout does not automatically delete:

Existing rows in player_stats (points, XP, wins/losses, voice stats, etc.)
Existing rows in server_activity_hourly (hourly message/voice activity rollups)
Leaderboard data and analytics data already in the database
Other historical database records (for example, past leaderboard placement, birthday entries, ticket ratings, giveaway participation)
Public display filtering: opted-out users are excluded from public leaderboard and Server Health user-list outputs in that server where this filtering is implemented — for example, weekly and match leaderboards (including weekly leaderboard cards), rank lookups (returning Unranked rather than a public rank), and Server Health user lists (including top users, participation mix, retention, and at-risk views).

Opt-out does not delete existing historical database records listed above. Historical activity data is retained by design and may still appear when you view your own stats (for example via /stats). Opt-out does not affect voluntary or social features that are separate from message/voice activity tracking unless specifically stated otherwise — for example, giveaway entries, birthday entries, cross-server event interest registrations, clip or video submission metadata, and ticket activity. Full user-data deletion requires a manual support request via the contact method above. Lurea does not currently provide a self-service command that erases all stored user history.

### Full user-data deletion request
Contact us at didemsahin2468@gmail.com or via the Discord Support Server: https://discord.gg/E9txAGt49U with:

Your Discord user ID (enable Developer Mode in Discord → right-click your profile → Copy User ID)
The server (guild) ID(s) involved, if applicable
What you want deleted (for example, stats, ticket ratings, birthday entry, giveaway participation)
We will review and process requests manually without undue delay. Under GDPR Article 12(3), we normally respond within one month of receiving your request. For complex or multiple requests, this period may be extended by up to two additional months where legally permitted; if an extension is necessary, we will inform you within the initial one-month period and explain the reasons. We may request identity or scope clarification where reasonably needed.

## What information to include in a deletion request
Please include as much of the following as applies:

Request type	Information needed
Server deletion	Guild ID, server name, your role (owner/admin), what to delete
User deletion	User ID, relevant guild ID(s), features involved
Both	Both sets above
Adding the date of your request and any reference (ticket number, prior conversation) helps us respond faster.

## What is deleted automatically when the bot leaves a server
When Lurea is removed from a Discord server, the bot attempts to delete operational data for that guild, including (non-exhaustive):

player_stats, XP, and server_activity_hourly rollups
Match records and related votes
Server setup, onboarding, and funnel data
Leaderboard and daily challenge settings and progress
Server health settings and analytics decision logs (server_health_settings, including any configured weekly_dm_user_ids administrator ID list — deleted on guild removal; disabling weekly health reports via /health_report_disable does not separately clear the weekly_dm_user_ids list)
Ticket settings, panel configuration (embed text, image/thumbnail URLs, button labels), ticket types, form question definitions, and open/closed ticket records (not ticket ratings — see below)
Welcome settings (including card/embed text and custom_background_url)
Rules verification settings (embed text, image/thumbnail URLs, and related configuration)
Giveaway records for that guild (including prize and description text, entries, and stored message_id / source_message_id references where present)
Cross-server event settings and host events for that guild (including stored event text fields and feed message_id references)
cross_server_event_interests rows where feed_guild_id matches the removed guild (direct delete); interest rows may also be deleted via CASCADE when a parent cross_server_events row is removed (for example, when the host guild removes the bot)
Per-user privacy preferences for that guild (user_guild_privacy_preferences)
revive_clip_submissions (clip/media and conversation-starter submission records for that guild, including stored message_id references and any legacy rows that contain attachment_url or original filenames from before the privacy refactor)
In-memory caches for that server (recent message, voice, and reaction event buffers)
Most guild configuration and operational records supported by automatic cleanup are removed when the bot leaves. Some feature data may remain until manual deletion where automatic cleanup is not technically implemented. Categories listed under What remains in the database after bot removal below are not covered by that automatic cleanup and require a manual deletion request.

## Admin-configured content, URLs, and message references (Lurea-controlled)
When guild-removal cleanup or an approved manual deletion request removes Lurea-held records for a server, the following Lurea-controlled data may be deleted, as applicable:

Custom background URLs (welcome cards, birthday cards)
Admin-configured embed text (welcome, rules verification, ticket panel, ticket type opening messages, cross-server events, giveaways)
Stored image/thumbnail URL strings (rules verification, ticket panel)
Ticket form question labels and placeholders (not user answers — answers are Discord-side only)
Cross-server event text fields (title, description, hero text, prize, rules, participation instructions)
Giveaway prize and description text
Stored message_id references tied to Lurea records (for example, clip submissions, conversation-starter rows, rules panel posts, ticket panel posts, cross-server feed posts, birthday announcement posts (birthday_posts), giveaway posts, staff-approved feedback source_message_id)
Deleting these records removes Lurea’s configuration and reference metadata. It does not delete the underlying Discord messages, channels, attachments, or third-party-hosted files those settings referenced or displayed.

Custom background URLs: removed from Lurea-controlled records when the relevant guild settings are deleted through guild removal or an applicable deletion request. Lurea does not control or guarantee deletion of the image file at the external URL host.

Legacy clip rows: older revive_clip_submissions rows may still contain attachment_url values or original attachment_filename values from before the privacy refactor. These are removed when the guild’s submission rows are deleted through server removal, parent event deletion, or manual cleanup. Lurea does not guarantee removal of the referenced file from Discord CDN.

## Clip/media submission records (revive_clip_submissions)
When an event ends: submission rows are not deleted. They remain in the database after the event completes.
When the bot is removed from a server: rows for that guild are deleted through guild-removal cleanup (see above).
Parent event deletion: rows may also be deleted if the parent revive_events row is removed (database cascade).
Time-based deletion: there is no automatic time-to-live for these rows.
Conversation-starter resubmission: if the same user submits again during the same conversation-starter event, the prior row for that user is deleted and replaced — this applies only within that event, not after the event ends.
Legacy rows: rows created before the privacy refactor may still contain Discord CDN URLs (attachment_url) or original filenames (attachment_filename). No automated process has been run to null or delete these values separately; they are subject to the same guild-removal and parent-event deletion behavior as other submission rows. Deleting Lurea-held legacy URL/filename metadata does not delete the underlying Discord-hosted media file.
## What remains in the database after bot removal
The following are not fully deleted by automatic guild-removal cleanup. Server administrators may request manual deletion through didemsahin2468@gmail.com or the Discord Support Server: https://discord.gg/E9txAGt49U

Data	What is kept
guild_registry	Soft-deleted: server ID, name, member count, join/last-seen/leave timestamps, inactive flag
birthday_settings	Per-guild birthday feature configuration, including custom_background_url
user_birthdays	User ID plus day, month, and optional year per guild
birthday_posts	Guild ID, user ID, birthday date, and stored message_id references for sent birthday posts
ticket_ratings	User ID, ticket reference, rating value, and timestamps where stored
auto_rescue_opportunity_interventions	guild_id, intervention_type, optional channel_id / message_id, JSONB metadata, created_at
auto_rescue_temporary_voice_sessions	Session metadata including guild ID, channel/message IDs, voice channel references, timestamps, and operational status fields
guild_invite_cache	Cached invite codes, inviter user IDs, channel IDs, and invite usage metadata
invite_attributions	Invited user ID, inviter user ID, invite code, attribution method, and join timestamps
role_panels / role_panel_options	Panel configuration, emoji identifiers, role IDs, channel IDs, message IDs, and creator/admin user IDs where stored
topgg_votes	Global per Discord user; not tied to a single guild
Birthday records: birthday_settings, user_birthdays, and birthday_posts are not automatically deleted by standard guild-removal cleanup. Manual deletion may be requested.

Invite tracking and reaction roles: guild_invite_cache, invite_attributions, role_panels, and role_panel_options are not automatically deleted by standard guild-removal cleanup. Manual deletion may be requested.

Ticket transcripts: Lurea does not store ticket message content in its database. Ticket channel content remains on Discord and is not covered by Lurea’s automatic guild-removal database cleanup.

If you need any of the above removed, submit a manual deletion request to didemsahin2468@gmail.com or via the Discord Support Server: https://discord.gg/E9txAGt49U

## Automatic retention while the bot is installed
server_activity_hourly: rows older than approximately 30 days are deleted automatically
Other tables (including revive_clip_submissions): no automated time-to-live deletion while the bot is installed; data is retained until guild removal cleanup or a manual deletion request. Clip/media submission rows are not deleted when an event ends
## Limitations / backups / logs
Database storage and backups: Lurea uses infrastructure providers located in Germany or the European Union where available (including Supabase for database hosting and Contabo for application hosting). Database availability, redundancy, and backup or recovery copy behavior may depend on the infrastructure provider and service plan in use; not every plan includes scheduled automatic backups. Lurea does not use backups for advertising, profiling, or unrelated purposes.

Deletion requests apply first to active Lurea-controlled systems. Personal data may temporarily remain in infrastructure backups, recovery copies, or provider-managed backup systems where such copies exist. Those copies are removed or overwritten according to the normal backup lifecycle and retention policies of the relevant infrastructure provider. The exact retention duration may vary by provider and service plan. Backup copies are not restored into active production systems solely to process a deletion request. If a backup is restored for disaster recovery, deletion requests that are still applicable should be re-applied to the restored active data where technically and legally required.
Server logs: Application logs are used for operational security, troubleshooting, and abuse prevention. Log retention depends on host configuration and may vary. Logs are accessible only to the operator. Some technical logs may persist temporarily after a deletion request depending on host log retention.
Discord-side data: Messages, channels, ticket channel content (including form answers), feedback embeds in the internal feedback channel, giveaway posts and giveaway feedback messages, welcome posts, rules/verification posts, cross-server event posts, and clip/media submission files already posted in Discord event channels are controlled by Discord and your server — Lurea cannot delete those on your behalf. Deleting Lurea-held configuration, metadata, or message_id references does not automatically delete the Discord content those records pointed to.
Third-party URL hosts: Custom background URLs and panel/embed image URLs point to external hosts. Lurea can delete the stored URL string from its database, but does not control or guarantee deletion of files at those external URLs.
Third-party systems: Lurea cannot guarantee deletion of data held by third-party services (such as Discord, Top.gg, Supabase infrastructure outside Lurea-controlled application data, or external image/CDN hosts) beyond what Lurea directly controls in its own database and operational systems
Feedback: /feedback submissions are sent as Discord embeds to an internal operator channel; feedback message content is not stored in the Lurea database. Lurea may store a guild-level flag that feedback was submitted. Deletion of feedback content must be handled in Discord
Giveaway feedback text: feedback message content submitted through giveaway feedback flows is posted to a configured Discord channel and is not stored in the Lurea database (only an optional source_message_id may be stored if staff later approve a bonus)
Legal and safety retention: We may retain minimal records where reasonably needed for abuse prevention, dispute resolution, or legal obligations
Processing time: Deletion requests are handled manually without undue delay. Under GDPR Article 12(3), we normally respond within one month of receiving your request. For complex or multiple requests, this period may be extended by up to two additional months where legally permitted; if an extension is necessary, we will inform you within the initial one-month period and explain the reasons. We may request identity or scope clarification where reasonably needed. Lurea does not promise instant deletion
## Contact
didemsahin2468@gmail.com or Discord Support Server: https://discord.gg/E9txAGt49U

### Related documents:

Privacy Policy
Terms of Service
Data Deletion
Impressum
