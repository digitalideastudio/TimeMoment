## Usage

Simply import the component:

```
import TimeMoment from 'TimeMoment';
```

and add to `components` section of your Vue other component:
```
components: {
    'time-moment': TimeMoment,
},
```

and you're all set! You can use it within a template like so:

```
<time-moment classes="time" :timeStart="post.created_at"></time-moment>
```

Note: timeStart is a required property and should be parseable datetime string (momentjs is used for working with datetime).