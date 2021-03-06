### Basic FlatFeed

```js
<StreamApp
  apiKey="3fjzn67nznwt"
  appId="41814"
  token="eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiZXhhbXBsZS11c2VyIn0.XEKjtzD2AIQMLXH6kfJlL8P_JV4CBYvcMsmQCFjyY2U"
>
  <FlatFeed
    Activity={(props) => (
      <Activity
        {...props}
        onClickHashtag={(word) => console.log(`clicked on ${word}`)}
        onClickMention={(word) => console.log(`clicked on ${word}`)}
      />
    )}
  />
</StreamApp>
```

### FlatFeed with custom ActivityFooter

```js
<StreamApp
  apiKey="3fjzn67nznwt"
  appId="41814"
  token="eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiZXhhbXBsZS11c2VyIn0.XEKjtzD2AIQMLXH6kfJlL8P_JV4CBYvcMsmQCFjyY2U"
>
  <FlatFeed
    options={{ limit: 3, withRecentReactions: true }}
    Activity={(props) => (
      <Activity
        {...props}
        onClickHashtag={(word) => console.log(`clicked on ${word}`)}
        onClickMention={(word) => console.log(`clicked on ${word}`)}
        Footer={() => (
          <React.Fragment>
            <ActivityFooter {...props} />
            <CommentList activityId={props.activity.id} />
          </React.Fragment>
        )}
      />
    )}
  />
</StreamApp>
```
