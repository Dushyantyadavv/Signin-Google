# Signin-Google
Sign In with Google
First to require passport-google-oauth20 AND mongoose-findorcreate, 

const GoogleStrategy = require('passport-google-oauth20').Strategy;
const findOrCreate = require("mongoose-findorcreate");
create it after mongoose schema --
userSchema.plugin(findOrCreate
and just after this add- 
passport.use(User.createStrategy());

passport.serializeUser( function(user, done) {
   done(null, user.id)
});
passport.deserializeUser(function(id, done){
    User.findById(id, function(err, user){
        done(err, user);
    });
});

Everything is inside the signWithGoogle file , Must check
