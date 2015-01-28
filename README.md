# FMX.InterstitialAd.Android
Admob Interstitials Snippet Code Using The Android JNI In Delphi XE7 Firemonkey


procedure TForm1.Button2Click(Sender: TObject);
begin
  IAdvertisment := TInterstitialAdvertisment.Create;
  IAdvertisment.SetOnCloseEvent(onAdClosedEvent);
  IAdvertisment.SetOnAdFailedToLoad(onAdFailedToLoadEvent);
  IAdvertisment.SetOnAdLeftApplication(onAdLeftApplicationEvent);
  IAdvertisment.SetOnAdOpened(onAdOpenedEvent);
  IAdvertisment.SetOnAdLoaded(onAdLoadedEvent);
  IAdvertisment.TestMode := True;
  IAdvertisment.SetAdUnitID('ca-app-pub-1543398996171627/8995432791');
  IAdvertisment.InitAdvertisment;
end;
