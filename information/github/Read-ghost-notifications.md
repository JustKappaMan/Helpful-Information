# Read "ghost" notifications

Solution found [here](https://github.com/orgs/community/discussions/6874#discussioncomment-2859125).

---

Sometimes something like this happens:
* Spammers mention you somewhere on GitHub;
* Moderators delete the message/gist/repo containing the mention;
* There are no notifications in your "Notifications" section but annoying blue dot is still there.

---

Execute the following command in terminal:
```shell
curl -X PUT \
    -H "Accept: application/vnd.github.v3+json" \
    -H "Authorization: token $TOKEN" \
    -d '{"last_read_at":"$TIMESTAMP"}'
    https://api.github.com/notifications \
```
> [!IMPORTANT]
> Don't forget to replace
> * `$TOKEN` with your [Personal Access Token](https://github.com/settings/tokens/new);
> * `$TIMESTAMP` with current time in ISO 8601 format: `YYYY-MM-DDTHH:MM:SSZ`.